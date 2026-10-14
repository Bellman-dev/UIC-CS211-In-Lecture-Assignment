- **NetID:** [jmart490]
- **Major:** [Computer Science]
- **Question that I chose from the memoization exercise:** [Count ways to reach the nth stair using step 1,2, or 3]
- **Link to the question article:** [https://www.geeksforgeeks.org/dsa/count-ways-reach-nth-stair-using-step-1-2-3/]
- **My solution:**
- 		
	// Should pass through the memo vector
	int countWays(int n, int &memo) {
		
		// int memo(n+1, -1);        //The memo should be initialized outside of the recursive function
		
		if (n == 0)
			{
			return 0;
		}
		if (n < 0) // Forgot to add this base case
			{
			return 0;
		}
		if (memo[n] != -1)
			{
			return memo[n];
		}
		// Didn't add the n-3, making it wrong
		return memo[n] = countWays(n - 1, memo) + countWays(n - 2, memo) + countWays(n - 3, memo);
	}