Virtual Pets Amok
====================
    
    Synopsis:
    ---------
    Welcome to the Virtual Pets Amok. 
    
    
     VirtualPetShelter Class
     =======================
     
    Instance Variable
    ------------------
	litterBox
    
    Constructor (for HashMap)
    --------------------------
	Map<String, VirtualPet> shelterPets = new HashMap<String, VirtualPet>();

    Methods
    ---------
	public int getLitterBox() - get/return litter box status
	public void cleanLitterBox() - cleans/decreases litter box status
	public void maintainAllRobo() - oil level, mood, and health increases
	public void cleanDogCages()	-  cleans cage. Cage messiness is set to 0. mood and health increase
	public void walkDogs() - method that increase health for all dogs
	public void intake(VirtualPet pet) - method for intake of virtual pet
	public void intake(RoboticPet pet) - method for intake of Robotic Pet
	public void intake(OrganicPet pet) - method for intake of Organic pet
	public void adoptPet(VirtualPet pet) -   Method to adopt a pet
	public void feedAllOrganic() -  Feeds all organic pets
	public void waterAllOrganic() - Waters all organic pets
    public void tickAllPets() - Tick all pets
	Collection<VirtualPet> pets()  -  Method returning collection of all pets in the shelter
    VirtualPet getPet(String name) -  Method to return a pet from the map by name
    public void playOne(VirtualPet player) - Method to play with one pet
	
	Virtual Pet class
	=================
	
	Instance variables
	------------------
	protected String name;
	protected String description;
	protected int health;
	protected int mood;
	
	Constructors 
	---------------
	Constructor for Random numbers used in tick
	protected Random generator = new Random();
	
	Constructor to create VirtualPet object and establishes default attributes for new pets
	public VirtualPet(String newName, String newDescription) {
		name = newName;
		description = newDescription;
		health = 50;
		mood = 50;
	}
	Abstract Methods
	----------------
	public abstract String getName() 
	public abstract int getHealth() 
	public abstract int getMood();
	public abstract void play();
	public abstract int tick();
	public abstract int generateRandom();
	
	@Override
	public String toString() {
		return ("[" + name + "] " + description); 
		
	
	Cat Class
	=========
	Abstract class that extends VirtualPet
	
	
	OrgCat Class
	============
	OrgCat extends Cat and implements OrganicPet interface
	
	Instance Variables
	---------------------
	protected int hunger;
	protected int thirst;
	
	Constructor
	-----------
	public OrgCat(String nameParam, String descriptionParam) {
		super(nameParam, descriptionParam);
		hunger = 50;
		thirst = 50;	}

	@Override
	public void feed() - decreases hunger and increases mood/happiness of pet an organic pet
	
	@Override
	public void water() - decreases thirst and increases mood/happiness of an organic cat	
	
	@Override
	public String getName() - gets/returns organic cat name

	@Override
	public int getHealth() - gets/returns health status of organic cat
	
	@Override
	public int getMood() - gets/returns mood of organic cat

	@Override
	public void play() - increases mood,hunger, and thirst for an organic cat when playing with an 
	                     organic cat
	@Override
	public int tick() - uses random number and generateRandom method simulate advance it time
		                for, hunger, thirst , and mood.
	@Override
	public int generateRandom() - returns random number. Used in tick method 
	
	@Override
	public int getHunger() - gets/returns hunger status of an organic cat

	@Override
	public int getThirst() - gets/returns thirst status of an organic cat
		
	public void decreaseHealth() - decreases health of an organic cat
		health -= 10;

    RoboCat Class
	=============
	public class RoboCat extends Cat implements RoboticPet
	
	Instance variables
	------------------
	int oilLevel;
	
	Constructor
	-----------
	public RoboCat(String nameParam, String descriptionParam) {
		super(nameParam, descriptionParam);
		oilLevel = 50;
	}

	@Override
	public String getName() - gets/returns name of robo cat

	@Override
	public int getHealth() - gets/returns name of a robo cat
	
	@Override
	public int getMood() - gets/returns mood of robo cat

	@Override
	public void play() - increases mood and decreases oil level for robo cat
	
	@Override
	public int tick() - uses random generator to decrease mood, and decrease oil level to simulate an advance
						in time
	@Override
	public int generateRandom() - generates random number for stats used in tick method to generate random
								 stats
	@Override
	public void oilPet() - increases oil level for robo cat
		oilLevel += 20;

	@Override
	public int getOilLevel() - gets/returns oil level of robo cat		
	
	@Override
		public void recharge() - increases mood and health of robo cat 
				
		
	Dog Class
	=========
	Abstract class that extends VirtualPet
	
	OrgDog Class
	============
	OrgDog extends Dog and implements OrganicPet interface
	
	Instance Variables
	---------------------
	protected int cageMessiness;
	protected int hunger;
	protected int thirst;

	Constructor
	-----------
	public OrgDog(String newName, String newDescription) {
		super(newName, newDescription);
		cageMessiness = 50;
		hunger = 50;
		thirst = 50;

	Methods
	-------
	public void feed() - decreases hunger, increases mood/happines, increases cage messiness for an 
						  organic dog

	public void water() - decreases thirst, increases mood/happiness, increases cageMessiness for an
		                  organic dog
	@Override
	public void walk() - decreases cage messiness, increases mood/happiness,increases health, increases hunger
						increases thirst of an organic dog
	@Override
	public void play() - increases mood/happiness, increases hunger, and increases thirst when playing
					      with an organic dog
	@Override
	public String getName() - gets/returns organic dog name
	
	@Override
	public int getHealth() - gets/returns health status of organic dog

	@Override
	public int getMood() - gets/returns mood of organic cat

	@Override
	public int tick() - uses random number and generateRandom method simulate advance it time
		                for, hunger, thirst, mood and cage messiness. returns cage messiness
	@Override
	public int generateRandom() - returns random number. Used in tick method

	@Override
	public int getHunger() - gets/returns hunger status of an organic dog

	@Override
	public int getThirst() - gets/returns thirst for an organic dog
	
	public void decreaseHealth() - decreases health for an organic dog.

	public int getCageMessiness() gets/return cage messiness status of an organic dog

	public void cleanCage() cage messiness is set to 0 for clean cage, mood increases and health increases
	
	RoboDog Class
	============
     
     public class RoboDog extends Dog implements RoboticPet {
	int oilLevel;
	}
	public RoboDog(String newName, String newDescription) {
		super(newName, newDescription);
		oilLevel = 50;
	}

	@Override
	public void walk() - increases mood/happiness, increases health ans decreases oil level for a robo dog

	@Override
	public String getName() - gets/returns name of robo dog

	@Override
	public int getHealth() - gets/returns health of a robo dog
	
	@Override
	public int getMood()  - gets/returns mood of a robo dog
	
	@Override
	public void play() - increases mood/happiness and decreases oil level

	@Override
	public int tick() - uses random number and generateRandom method simulate advance it time
		                .Decreases mood and decreases oil level of robo dog
	@Override
	public int generateRandom() - returns random number. Used in tick method

	@Override
	public void oilPet() - increases oil level for robo dog
		oilLevel += 20;

	@Override
	public int getOilLevel() gets and returns oil level for a robo dog

	@Override
	public void recharge() - increases mood and health of robo dog
	
	
	RoboticPet - Interface - These methods are implemented in the RoboDog and RoboCat classes
	=========================
	public interface RoboticPet {

	String getName();
	public void oilPet();
	public int getOilLevel();
	public void recharge();

} 

	OrganicPet - Interface - These methods are implemented in the OrgDog and OrgCat classes
	============================
	public interface OrganicPet {

	String getName();
	void feed();
	void water();
	int tick();
	int getHunger();
	int getThirst();

}


	
     