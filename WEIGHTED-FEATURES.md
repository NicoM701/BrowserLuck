# 🎯 Weighted Glücksrad - Feature Documentation

## 📋 New Features

The **gluecksrad-weighted.html** file extends the original spinning wheel with advanced probability control!

## ⚖️ Weight System

### 🎪 How It Works

**Input Format:**
```
Gold 10%
Silver 15%
Bronze
Nothing
```

### 🔧 Parsing Logic

1. **Weighted Items**: Items ending with `X%` (e.g., "Gold 10%")
2. **Unweighted Items**: Regular text without percentage
3. **Empty Slots**: Automatically created when total < 100%

### 📊 Distribution Examples

**Example 1: Mixed Weights**
```
Gold 10%          → 10% chance
Silver 20%        → 20% chance  
Bronze            → 35% chance (half of remaining 70%)
Nothing           → 35% chance (half of remaining 70%)
```

**Example 2: Partial Weights**
```
Jackpot 5%        → 5% chance
Bonus 15%         → 15% chance
[Empty Space]     → 80% chance (automatic)
```

**Example 3: Error Handling**
```
Item1 60%
Item2 50%         → ERROR: 110% total (>100%)
```

## 🎨 Visual Indicators

- **🔴 Red segments**: Weighted items (have %)
- **🌈 Colored segments**: Unweighted items (split equally)
- **⚫ Gray segments**: Empty slots ([Leer])
- **❌ Error display**: When percentages exceed 100%

## 🧮 Mathematical Accuracy

- **Precise calculations**: Segments sized exactly to percentages
- **Fair distribution**: Unweighted items split remaining space equally
- **Accurate winner detection**: Pointer calculation respects weighted segment sizes

## 🛠️ Technical Implementation

### Weight Parsing
```javascript
const percentMatch = item.match(/(.+?)\s*(\d+(?:\.\d+)?)%\s*$/);
```

### Segment Calculation
```javascript
const segmentAngle = (segment.percentage / 100) * (2 * Math.PI);
```

### Winner Detection
```javascript
// Finds segment based on cumulative angle ranges
let cumulativeAngle = 0;
for (segment in weightedSegments) {
    if (pointerAngle >= cumulativeAngle && 
        pointerAngle < cumulativeAngle + segmentAngle) {
        return segmentIndex;
    }
    cumulativeAngle += segmentAngle;
}
```

## 🎯 Use Cases

### 🎮 Gaming
- **Loot boxes**: "Legendary 2%, Epic 8%, Rare 20%, Common 70%"
- **Drop rates**: Exact probability control for items

### 🏆 Contests  
- **Prize wheels**: "Grand Prize 1%, Second Prize 4%, Third Prize 15%, Consolation 80%"
- **Raffles**: Weighted by ticket count

### 📊 Statistics
- **Surveys**: Weight responses by demographic
- **Testing**: Controlled probability distributions

### 🎲 Gambling (Simulation)
- **Slot machines**: Realistic probability modeling
- **Lottery**: True-to-life odds simulation

## 🔍 Advanced Features

### Error Handling
- **Real-time validation**: Instant feedback on percentage totals
- **Visual error display**: Red error box with clear message
- **Graceful degradation**: Wheel disabled until fixed

### Smart Text Sizing
- **Adaptive fonts**: Adjusts to segment size (small segments = smaller text)
- **Vertical text**: Automatically switches for narrow segments
- **Truncation**: Long text shortened with "..." when needed

### Color Coding
- **Type-based colors**: Different colors for weighted vs unweighted
- **Empty slot indication**: Distinct gray color for empty space
- **Visual hierarchy**: Easy to distinguish segment types

## 🚀 Performance

- **Efficient parsing**: Regex-based percentage detection
- **Real-time updates**: Instant recalculation on text change
- **Smooth animation**: Same 60fps performance as original

## 🎪 Examples to Try

### Realistic Gaming Loot
```
Mythic Item 0.1%
Legendary Item 1.9%
Epic Item 8%
Rare Item 20%
Common Item 70%
```

### Contest Prizes
```
Grand Prize 1%
Second Prize 5%
Third Prize 14%
Participation Prize 80%
```

### Skill-Based Outcomes
```
Critical Success 5%
Success 45%
Partial Success 35%
Failure 15%
```

---

**✨ The weighted system maintains all original features while adding precise probability control for professional applications!**