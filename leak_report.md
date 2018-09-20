# Leak report

Memory is allocated to result to keep track of each character. The memory leak
occurs in line 41 of the strip function, line 62 of the is_clean
function, and in line 88 in main. The characters are passed from function to
function all the way to main but are never freed at any step along the way.

To fix the memory leak, we need to free up memory in the function is_clean.
After result has been updated with a string comparison, we can check if the
cleaned string is null. If it isn't, then we free up the memory. We can't free
memory for a null string.

