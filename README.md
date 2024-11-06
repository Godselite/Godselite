// Smokery Nose - The Magical, Calming, and Slightly Dangerous Scent

class SmokeryNose {
  constructor() {
    this.smokeLevel = 0;
    this.isTroubled = false;
    this.isHungry = false;
    this.isPregnant = false;
  }

  // The magical effect of the Smokery Nose that calms people
  calmPeople() {
    console.log("The Smokery Nose begins to release a soft, calming mist...");
    this.smokeLevel += 1;
    this.isTroubled = false;  // Calms down the troubled souls
    this.isHungry = false;    // Eases hunger
    this._emitScent();
  }

  // The warning: do not inhale if you want to avoid unexpected results
  _emitScent() {
    if (this.smokeLevel >= 5) {
      console.log("WARNING: The Smokery Nose has reached dangerous levels!");
      console.log("If you inhale too much, you might end up with an unexpected pregnancy!");
      this.isPregnant = true;
    } else {
      console.log("The scent is sweet, calming, and delightful. Feel at peace.");
    }
  }

  // Reset the nose's effects after a while
  resetNose() {
    console.log("The Smokery Nose effect fades away, and you feel normal again.");
    this.smokeLevel = 0;
    this.isTroubled = false;
    this.isHungry = false;
    this.isPregnant = false;
  }

  // Simulate different scenarios based on user's status
  useNose(situation) {
    if (situation === "trouble") {
      this.isTroubled = true;
      console.log("People around are troubled... releasing calming scent...");
      this.calmPeople();
    } else if (situation === "hunger") {
      this.isHungry = true;
      console.log("People are hungry... releasing soothing aroma to ease hunger...");
      this.calmPeople();
    } else if (situation === "runaway") {
      console.log("Someone warns: You better stay away or risk pregnancy!");
      this.smokeLevel = 5;  // Mimicking the point of dangerous level
      this._emitScent();
    } else {
      console.log("No current situation... just let the Smokery Nose relax!");
      this.resetNose();
    }
  }
}

// Example usage:
const smokery = new SmokeryNose();

// Calming people in trouble
smokery.useNose("trouble");

// Calming hunger
smokery.useNose("hunger");

// Warning before pregnancy
smokery.useNose("runaway");

// Reset the Smokery Nose effect
smokery.resetNose();
