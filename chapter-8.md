Separate functoriality is not enough to prove joint functoriality: 

Imagine a constant functor that goes from Set to an object in Set and
then another constant functor that goes from Set to another object in Set.

1. bimap (Pair a b) f g = Pair (f a) (g b)

2. toNormalMaybe (Left constUnit) = Nothing
   toNormalMaybe (Right (Identity a)) = Just a

   Reverse for the opposite direction
3. bimap Nil = Nil
   bimap (Cons a b) = Cons (f a) (f b)

4. The reasonins is basically all variants of why Const is a functor
5. Scala looks the same
6. No idea
