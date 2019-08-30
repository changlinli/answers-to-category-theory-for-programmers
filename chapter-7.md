1. No, this maps identity to the constant function, hence breaking functor laws
2. Identity is preserved because fmap is composition so we're just composing two
   identity functions together. Associativity follows by composition
   associativity.
3. Do it in Scala! In the same way
4. ```
   fmap f Nil = Nil
   fmap f (x : xs) = f x : (fmap f xs)
   ```

   Induction: base case holds for identity and composition
   Inductive step identity: assume that `(fmap f xs) = xs`, then `f x = x` by
   identity we have `x : xs = x : xs` so done.
   Inductive step composition: assume that `(fmap (f . g) xs) = (fmap f . fmap g) xs`
   ```
   (fmap f) . (fmap g) (x : xs) 
     = (fmap f) ((fmap g) (x : xs)
     = (fmap f) (g x : fmap g xs)
     = (f (g x) : (fmap f (fmap g xs)))
     = (f (g x) : ((fmap f . fmap g) xs))
     -- Inductive step
     = (f (g x) : (fmap (f . g) xs))
     = ((f . g) x : (fmap (f . g) xs))
     = fmap (f . g) (x : xs)
   ```

