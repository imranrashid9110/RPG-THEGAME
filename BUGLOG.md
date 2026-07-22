# BUGLOG

Name: 

## Bug #1
Symtomn: Broken header gaurd in character h, has extra _
cause: Since they did not match, the header guard did not prevent multiple inclusions.
fix: #define CHARACTER_H

## Bug #2
-symptomn:Drinking a potion did not actually heal the hero or decrease the potion count
cause: drinkPotion() passed the Character object by value, creating a copy instead of modifying the original hero
fix: Change character hero to Character& hero


## Bug #3
Symptom: The hero fought 4 monsters instead of the required 3 monsters.
cause: the for loop used i<= 3
fix: is i < 3

## Bug #4 
Symptom: Battles continued even after the hero or monster had already died.
cause: The battle loop used the logical OR operator (||), so the loop continued while either combatant was still alive.
fix: change hero.isAlive() || monster.isAlive() to hero.isAlive() && monster.isAlive()

## Bug #5
symptom: The hero’s HP could become greater than the maximum HP after drinking a potion.
cause: drinkPotion() added 10 HP without checking whether hero.hp exceeded hero.maxHp
fix: Added a condition that checks if the hero's HP is greater than maxHp. If it is, the hero's HP is reset to maxHp so it cannot exceed the maximum health.


## Bug #6
symptom: Monsters had very low HP and unusually high attack values.
cause: In monster.cpp, the HP and attack arguments were passed to the Character constructor in the wrong order.
fix: Swapped the HP and attack arguments in the Character constructor call. This makes each monster use the correct HP and attack values instead of having them reversed.
