1. ```
   natural :: Maybe a -> List a
   natural (Just a) = a :: []
   natural Nothing = []
   ```

   naturality condition states that 
   `(fmap f :: List a -> List a) . natural = natural . (fmap f :: Maybe a -> Maybe a)`
   Let's call the first (fmap f) listF and the second (fmap f) maybeF. Assume
   listF . natural /= natural . maybeF. Then there is an x such that 
   
   ```
    (listF .  natural) x /= (natural . maybeF) x
   ```

   Let x be (). There is only one implementation of `f`. Therefore there is only
   one implementation of `listF` and `maybeF`. A tedious calculation is enough
   to show that equality must hold in this case. By parametricity, this means
   equality must always hold for all types.

2. ```
   natural0 :: Reader () a -> [a]
   natural0 f = []
   
   natural1 :: Reader () a -> [a]
   natural1 f = [ f () ]
   ```

   There are an infinite number of lists of (), one for each length of list.
