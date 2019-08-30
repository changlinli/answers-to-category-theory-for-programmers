1. Map Just to Right and Nothing to Left ()
2. Just make it a method and go to town.
3. You have to touch Circle and Rec, example of the expression problem (what
   happens if you wanted to add a new shape?)
4. Ah there you go.
5. from :: Either a a -> (Bool, a)
   from (Left a) = (True, a)
   from (Right a) = (False, a)

   to :: (Bool, a) -> Either a a
   to (True, a) = Left a
   to (False, a) = Right a

