# How to implement a Binary Search in JavaScript

````
let exampleArray = [1, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59];

const binarySearch = (array, target) => {
  //number of iterations
  let loops = 0
  
  // Define Start and End Index
  let startIndex = 0;
  let endIndex = array.length - 1;
  
  // While Start Index is less than or equal to End Index
  while(startIndex <= endIndex) {
  
    // Define Middle Index (This will change when comparing )
    let middleIndex = Math.floor((startIndex + endIndex) / 2);
    
    // Compare Middle Index with Target for match
    if(target === array[middleIndex]) {
      loops ++
      return `Target was found at index ${middleIndex} in ${loops} iterations`;
    }
    
    // Search Right Side Of Array
    if(target > array[middleIndex]) {
      console.log("Searching the right side of Array")
      loops ++
      
      // Assign Start Index and increase the Index by 1 to narrow search
      startIndex = middleIndex + 1;
    }
    
    // Search Left Side Of Array
    if(target < array[middleIndex]) {
      // Assign End Index and increase the Index by 1 to narrow search
      console.log("Searching the left side of array")
      loops ++
      endIndex = middleIndex - 1;
    }
    
    // Not found in this iteration of the loop. Looping again.
    else {
      loops ++
      console.log("Not Found this loop iteration. Looping another iteration.")
    }
  }
  
  // If Target Is Not Found
  console.log("Target value not found in array");
}

binarySearch(exampleArray, 37)
````
