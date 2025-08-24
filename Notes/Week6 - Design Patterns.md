# Design patterns
* Design patterns in Java are proven solutions to common software design problems. 
* `Design patterns` represent `established best practices` for structuring code and object interactions, 
leading to more `maintainable, flexible, and scalable` applications. 
* `Design patterns` are not concrete implementations to be copied directly but rather 
`templates or guidelines` that can be adapted to specific contexts.

## Types of Design Patterns
  * Creational — object creation (Singleton, Factory, ...)
  
 * Structural — composition of classes/objects (Adapter, Decorator, ...)
  
  * Behavioral — communication between objects (Strategy, Observer, ...)

## Creational Patterns
  ### Singleton
  * Ensures only one instance exists for a class.
  
  ```java
  class Singleton {
      private static final Singleton instance = new Singleton();
      private Singleton() {}
      public static Singleton getInstance() { return instance; }
  }
  ```
  ### Factory Method
  * Create objects without specifying the concrete class.
  
  ```java
  interface Payment { void pay(double amount); }
  class CreditCard implements Payment { public void pay(double amt) { System.out.println("Credit: " + amt); } }
  class DebitCard implements Payment { public void pay(double amt) { System.out.println("Debit: " + amt); } }
  
  class PaymentFactory {
      static Payment getPayment(String type) {
          if (type.equals("credit")) return new CreditCard();
          else return new DebitCard();
      }
  }
  // Usage: Payment p = PaymentFactory.getPayment("credit");
  ```
## Structural Patterns
  ### Adapter
  Allows incompatible classes to work together.
  
  ```java
  interface MediaPlayer { void play(String filename); }
  class MP3Player implements MediaPlayer { public void play(String f) { System.out.println("Playing mp3: " + f); } }
  class MP4Player { void playMp4(String f) { System.out.println("Playing mp4: " + f); } }
  
  // Adapter: wraps MP4Player so it looks like a MediaPlayer
  class MP4Adapter implements MediaPlayer {
      private MP4Player mp4 = new MP4Player();
      public void play(String f) { mp4.playMp4(f); }
  }
  // Usage: MediaPlayer player = new MP4Adapter(); player.play("file.mp4");
  ```
  ### Decorator
  * Add functionality to objects, dynamically.

## Behavioral Patterns
  ### Strategy
  * Define a family of algorithms, interchangeably.
  
  ```java
  interface DiscountStrategy { double apply(double amt); }
  class NoDiscount implements DiscountStrategy { public double apply(double amt) { return amt; } }
  class TenPercentOff implements DiscountStrategy { public double apply(double amt) { return amt * 0.9; } }
  
  class Checkout {
      private DiscountStrategy ds;
      public Checkout(DiscountStrategy ds) { this.ds = ds; }
      public double finalAmount(double amt) { return ds.apply(amt); }
  }
  // Usage: new Checkout(new TenPercentOff()).finalAmount(100.0);
  ```
    
    ```java
    interface Coffee { String getDescription(); double cost(); }
    class BasicCoffee implements Coffee {
        public String getDescription() { return "Plain coffee"; }
        public double cost() { return 2.0; }
    }
    class MilkDecorator implements Coffee {
        private Coffee coffee;
        public MilkDecorator(Coffee c) { coffee = c; }
        public String getDescription() { return coffee.getDescription() + ", milk"; }
        public double cost() { return coffee.cost() + 0.5; }
    }
    // Usage: Coffee c = new MilkDecorator(new BasicCoffee());
    ```
  ### Observer
  * Notify interested objects of changes (pub-sub).
  
  ```java
  interface Observer { void update(String msg); }
  class EmailAlert implements Observer { public void update(String msg) { System.out.println("Email: " + msg); } }
  class Notifier {
      List<Observer> subs = new ArrayList<>();
      void subscribe(Observer o) { subs.add(o); }
      void notifyAll(String msg) { for (Observer o : subs) o.update(msg); }
  }
  // Usage: Notifier n = new Notifier(); n.subscribe(new EmailAlert()); n.notifyAll("Event!");
  ```
## Summary
<div class="w-full overflow-x-auto md:max-w-[90vw] border-borderMain/50 ring-borderMain/50 divide-borderMain/50 bg-transparent"><table class="border-borderMain my-[1em] w-full table-auto border"><thead class="bg-offset"><tr><th class="border-borderMain p-sm break-normal border text-left align-top">Pattern Type</th><th class="border-borderMain p-sm break-normal border text-left align-top">Example Pattern</th><th class="border-borderMain p-sm break-normal border text-left align-top">Key Benefit</th></tr></thead><tbody><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Creational</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Singleton</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Only one instance</td></tr><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Creational</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Factory</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Decouples creation from usage</td></tr><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Structural</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Adapter</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Integrates incompatible interfaces</td></tr><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Structural</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Decorator</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Adds features at runtime</td></tr><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Behavioral</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Strategy</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Switch algorithms flexibly</td></tr><tr><td class="border-borderMain px-sm min-w-[48px] break-normal border">Behavioral</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Observer</td><td class="border-borderMain px-sm min-w-[48px] break-normal border">Event-driven architecture</td></tr></tbody></table></div>
