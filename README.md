import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

/**
 * Represents different types of EC2 instances, detailing their capabilities and whether they are equipped with AWS Inferentia.
 */
class InstanceType {
    private String name;
    private boolean isInferentiaEnabled;
    private double computePower;

    public InstanceType(String name, boolean isInferentiaEnabled, double computePower) {
        this.name = name;
        this.isInferentiaEnabled = isInferentiaEnabled;
        this.computePower = computePower;
    }

    public String getName() {
        return name;
    }

    public boolean isInferentiaEnabled() {
        return isInferentiaEnabled;
    }

    public double getComputePower() {
        return computePower;
    }
}

/**
 * Manages performance metrics for different EC2 instances, providing functionality to add and retrieve performance data.
 */
class PerformanceMetrics {
    private HashMap<String, Double> metrics;

    public PerformanceMetrics() {
        metrics = new HashMap<>();
    }

    public void addMetric(String instanceName, double performance) {
        metrics.put(instanceName, performance);
    }

    public double getMetric(String instanceName) {
        return metrics.getOrDefault(instanceName, 0.0);
    }

    public void printMetrics() {
        metrics.forEach((instance, perf) -> {
            System.out.println("Instance: " + instance + " - Inference Performance: " + perf);
        });
    }
}

/**
 * Simulation engine that manages the setup and execution of performance simulations for various instance types.
 */
class SimulationEngine {
    private List<InstanceType> instances;
    private PerformanceMetrics performanceMetrics;

    public SimulationEngine() {
        instances = new ArrayList<>();
        performanceMetrics = new PerformanceMetrics();
    }

    public void addInstanceType(InstanceType instance) {
        instances.add(instance);
    }

    public void simulate() {
        for (InstanceType instance : instances) {
            double performance = calculatePerformance(instance);
            performanceMetrics.addMetric(instance.getName(), performance);
        }
    }

    private double calculatePerformance(InstanceType instance) {
        return instance.getComputePower() * (instance.isInferentiaEnabled() ? 1.2 : 1.0);
    }

    public void displayResults() {
        performanceMetrics.printMetrics();
    }
}

/**
 * Main application class containing the entry point for the simulator. Sets up the simulation and displays the results.
 */
public class App {
    public static void main(String[] args) {
        SimulationEngine engine = new SimulationEngine();
        
        engine.addInstanceType(new InstanceType("t2.micro", false, 1.0));
        engine.addInstanceType(new InstanceType("c5.large", true, 2.0));
        engine.addInstanceType(new InstanceType("inf1.xlarge", true, 3.5));

        engine.simulate();
        engine.displayResults();
    }
}
