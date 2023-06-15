

## Passwords In Code
1. Store password always in character array 
	1. Reasons: 
		1. Immutable nature: Unlike `String` objects, `char` arrays are mutable, which means you have more control over their contents. You can explicitly overwrite the array elements with random or null values once the password is no longer needed. This helps reduce the likelihood of the password being exposed in memory.
		2. Garbage collection: `String` objects in Java are immutable, meaning they cannot be modified. When you assign a password to a `String` object, it remains in memory until garbage collected, and during that time, it can be accessed by other parts of the program. This makes it potentially vulnerable to memory dump attacks or unintentional exposure. `char` arrays, on the other hand, can be explicitly cleared or overwritten, reducing the time the password remains in memory.
		3. Immutable string pool: Java maintains a string pool for `String` objects, which can store and reuse string literals. This means that if a password is assigned to a `String` object, it may persist in memory in the string pool even after the reference to the object is removed. This poses a security risk as the password could potentially be retrieved from the string pool.
		4. Security-sensitive operations: Passwords are sensitive pieces of information, and their storage should follow security best practices. Java provides `javax.security.auth.Destroyable` interface, which can be implemented by `char` arrays to securely destroy sensitive information. By implementing this interface, you can ensure that the password can be securely wiped from memory when no longer needed.
2. 
   
   
   
   
#Java