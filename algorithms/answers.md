## Exercise I

(a) O(n)

(b) O(log n)

(c) O(sqrt(n))

(d) O(n log n)

(e) O(n^4)

(f) O(n)

(g) O(n)

## Exercise II

(a)
```
function highestDifference(arr) {
  let highest = Math.max(arr[0], arr[1]);
  let lowest  = Math.min(arr[0], arr[1]);

  for (let i = 2; i < arr.length; i++) {
    highest = Math.max(highest, arr[i]);
    lowest  = Math.min(lowest, arr[i]);
  }
  
  return highest - lowest;
}

let n = [6, 1, 21, 67, 23, 546, 2, 7, 112];
console.log(highestDifference(n));
```

(b)
```
function saveTheEggs(building) {
  let length = building.length;
  let drop = Math.floor(building.length / 2);
  let diff = drop;
  let previousDrop = 0;
  let lost = 0;
  let dropped = 0;

  for (let i = 0; i < building.length; i++) {
    dropped++;

    if (building[drop] === 'splat') {
      diff = Math.floor(diff / 2);
      drop -= diff;
      lost++;
    }
    if (building[drop] === 'safe') {
      diff = Math.floor(drop / 2);
      drop += diff;
    }

    if (previousDrop === drop) break;
    previousDrop = drop;
  }
  
  return { eggsDropped: dropped, eggsLost: lost, fancyFloor: drop - 1 };
}
```

for testing:
```
let building = [
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'safe',
  'splat',
  'splat',
  'splat',
  'splat',
  'splat',
  'splat',
  'splat',
  'splat',
  'splat',
];

results = saveTheEggs(building);
console.log('Eggs Dropped:', results.eggsDropped);
console.log('Eggs Lost:', results.eggsLost);
console.log('Fancy Floor:', results.fancyFloor);
```

## Exercise III

(a)