# Whiteboarding
#### By Shanen Cross

### Code from answering a mock whiteboarding question

Determines whether all elements in a string are unique

May not convert string to array or use array methods to solve this problem

returns boolean

Input: 'hello'
Ouptut: false

Input: 'copyright'
Output: true

input: string
output: boolean

function isUnique(input) {
	if (typeof input !== "string") {
  	return false;
  }

	let encounteredCharacters = Set();
  
  const lowerCaseInput = input.ToLowerCase();
  
  for (let character of lowerCaseInput) {
  	if (encounteredCharacters.has(character)) {
    	return false;
    }
    encounteredCharacters.add(character);
  }
  
  return true;
}

// recursive version
function isUnique(input, encounteredCharacters=new Set()) {
  if (typeof input !== "string") {
  	return false;
  }
  const lowerCaseInput = input.ToLowerCase();
  
  if (lowerCaseInput === "") {
  	return true;
  }
  if (encounteredCharacters.has(lowerCaseInput[0])) {
  	return false
  }
  
  encounteredCharacters.add(lowerCaseInput[0]);
  return isUnique(lowerCaseInput.substring(1), encounteredCharacters);
}
