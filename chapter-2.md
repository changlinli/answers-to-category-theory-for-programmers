1. Memoize implementation in Scala

def memoize[A, B](f: A => B): A => B ={
    val map: ConcurrentHashMap[A, B] = Map.empty
    (x: A) => map.get(x) match {
         case Some(b) => b
         None =>
              val result = f(x)
              map.put(result)
              result
    }
}
2. No it doesn't
3. No it doesn't (repeated calls still don't work)
4. a. Is pure
   b. Not pure
   c. Not pure
   d. Not pure (static persists across function calls)
5. 4: identity, not, always true, always false
6. Void -> Void (1 function)
   Void -> () (1 function)
   Void -> Bool (1 function)
   () -> () (1 function)
   () -> Bool (2 functions)
   Bool -> Bool (4 functions)
   Bool -> () (1 functions)
