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

3. ```
   natural0 :: Reader Bool a -> Maybe a
   natural0 f = Nothing
   
   natural1 :: Reader Bool a -> Maybe a
   natural1 f = Just (f True)
   ```

   There are a lot fewer possible implementations here.

4. Given natural transformations $\alpha : F \to F'$ and $\beta : G \to G'$ where
   $F, F' : C \to D$ and $G, G' : D \to E$, we want to show that $\alpha \cdot
   \beta$ satisfies naturality. Note that $\alpha \cdot \beta : F \cdot G \to F'
   \cdot G'$. Let $\gamma = \alpha \cdot \beta$ and $H = F \cdot G$ and $H' = F'
   \cdot G'$. Lots of rewrite and replace rules follow. But it's pretty
   straightforward (basically each rewrite, because naturality flips the order
   of functor and component of natural composition order, lines up everything just
   right).

5. Haha no.

6. ???
