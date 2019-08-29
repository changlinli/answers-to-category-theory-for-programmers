1. Assume there are two terminal objects t1 and t2. Because t1 is terminal there
   must be a unique morphism from t2 to t1 and vice versa for t2. This yields
   our unique isomorphism between t1 and t2.
2. The smaller element of the two. The morphisms between the two follow
   immediately. Factorizing follows by transivity of the ordering relation.
3. The larger element of the two. Reverse argument of 2.
4. sealed trait in Scala. More generally we can use Scott encoding.
5. m :: Either Int Bool -> Int
   m Left i = i
   m Right True = 0
   m Right False = 1
   m factorizes.
6. You have a conflict with 0 and 1. In particular when choosing a factorizing
   function m you need to decide how to map 0 and 1 from Int to Either Int Bool,
   but any choice you make will fail to factorize either i or j.
7. This is also a valid coproduct. It is uniquely isomorphic to Either via the
   obvious construction.
8. Overly ambitious either. Either Int (Either Int Bool). This yields 
