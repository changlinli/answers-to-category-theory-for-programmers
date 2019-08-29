1. Objects are types, arrows are -> Maybe, 
   composition is compose f g = \x -> g x >>= f x
2. safe_reciprocal x = if (x == 0) then Nothing else Just (1 / x)
3. compose safe_root safe_reciprocal
