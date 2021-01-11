/**
 * The following is the function where the solution shall be written
 */

// return all variations of integers in DESCENDING order

function solution(input) {
  let nums = input.replace(/\D/g, ""); // remove all non-integers from input
  let arr = [];
  let variations = [];
  let numbers = nums.split("");
  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 0) {
      arr.push(numbers[i]); // adds only positive integers to array
    }
  }

  // rotate integers in array for each 'count'
  let rotate = (indexA, indexB) => {
    let swapNum = arr[indexA];
    arr[indexA] = arr[indexB];
    arr[indexB] = swapNum; // swap indexA with indexB
  };

  // use array length as argument
  function generateSolution(length) {
    if (length === 1) {
      variations.push(arr.join("")); // removes commas between integers in each variation and adds value to 'variations' array
    } else {
      for (let i = 0; i < length; ++i) {
        generateSolution(length - 1); // length - 1 because 0 index

        rotate(length % 2 ? 0 : i, length - 1); // when length is odd, swap first, second ... etc number with last number. If length is even, swap first with last
      }
    }
  }
  generateSolution(arr.length);
  if (variations.length === 0) {
    return "no numbers entered";
  }
  return [...new Set(variations)].sort((a, b) => b - a); // filters out duplicate values and returns them in descending order
}

// example input
console.log(solution(",%634*o)"));
// console.log(solution('34rf76'));
