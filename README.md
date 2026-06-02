# MRRN-Guesser

## STRUCTURE
- still images
- 15 sec timer

## FEATURES & DESIGN
### Sound Effects:
- among us role reveal sound - when new map
- vine boom - when you click on map
- csgo c4 - countdown
- csgo c4 explosion - if no guess
- faaaahh - if score <2500
- ding - score 2500 - 450
- terrorist win - score 4500+
- pvz win - score 5000

### Features:
- Share score at the end of the round button, people enter usernames (MAKE SURE TO HAVE FILTERS), if guy pressed on share they get teleported to leaderboard to see other scores
- Leaderboard (+confetti & sfx when you finish the game)
- **20 photos / 5 photos per round**

### Algo?:
function calculateScore(distanceInMeters) {
    // 1. Perfect score condition
    if (distanceInMeters < 10) {
        return 5000;
    }
    
    // 2. Out of bounds condition
    if (distanceInMeters > 1000) {
        return 0;
    }
    
    // 3. Linear scaling between 10m and 1000m
    const maxScore = 5000;
    const distanceWindow = 1000 - 10; // 990 meters total sliding scale
    
    const score = (1 - (distanceInMeters - 10) / distanceWindow) * maxScore;
    
    return Math.round(score);
}

