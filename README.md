Nick Bearup

Project #1 Submission

1)

FOR K=2

spark-submit --class "project_1.main" --master "local[*]" target/scala-2.12/project_1_2.12-1.0.jar this_is_a_bitcoin_block_of_56315834 2 10000000 output:

==================================
found. count:39121
(1411720824this_is_a_bitcoin_block_of_56315834,00f6b29f2c138d770fd56c24d5af306691cbabd0b2a13ccf4951d8747e049a63)
Time elapsed:24s


FOR K=3

spark-submit --class "project_1.main" --master "local[*]" target/scala-2.12/project_1_2.12-1.0.jar this_is_a_bitcoin_block_of_56315834 3 10000000 output:

==================================
found. count:2430
(884371629this_is_a_bitcoin_block_of_56315834,000dac8a0c6183f8c90a77477c38841b5e7a69d100169c74814f7d08a27727d1)
Time elapsed:22s


FOR K=4

spark-submit --class "project_1.main" --master "local[*]" target/scala-2.12/project_1_2.12-1.0.jar this_is_a_bitcoin_block_of_56315834 4 10000000 output:

==================================
found. count:142
(308888489this_is_a_bitcoin_block_of_56315834,00000cb80b52032f2efa9c72945d0a5ea1d2687e9c2082f08c73cd4e5995eea1)
Time elapsed:22s








FOR K=5

spark-submit --class "project_1.main" --master "local[*]" target/scala-2.12/project_1_2.12-1.0.jar this_is_a_bitcoin_block_of_56315834 5 10000000 output:

==================================
found. count:11
(1790749159this_is_a_bitcoin_block_of_56315834,0000046ea70dcfb1631d84efc7c8de23a7b2dcf9520ed7409d34f9cf14eb147f)
Time elapsed:22s


FOR K=6

spark-submit --class "project_1.main" --master "local[*]" target/scala-2.12/project_1_2.12-1.0.jar this_is_a_bitcoin_block_of_56315834 6 100000000 output:

==================================
found. count:7
(1768414124this_is_a_bitcoin_block_of_56315834,000000fb86cb40a12f62c59a7504091d73d9086accc7195935e9609c067d915c)
Time elapsed:182s



2)

Elapsed time:
6 min 21 sec
Status:
Succeeded
Arguments
this_is_a_bitcoin_bucket_of_56315834
7
100000000
Job output
==================================
found. count:1
(383261996this_is_a_bitcoin_bucket_of_56315834,0000000855bdce2683599d6a7a873a5c11ae1b4a30a904e42be975b2daf4d0c7)
Time elapsed:372s
==================================



3)

I edited the lines 56 through 59 to take out the random functions, which now shows:

val nonce = sc.range(0, trials).mapPartitionsWithIndex((indx, iter) => {
      val rand = new scala.util(indx + seed)
      iter.map(x => nextInt(Int.MaxValue - 1) + 1)
    })

When I tested it again, the count value was around the same as the value with the old program. In theory, I feel like this should make it more efficient, since it takes out the additional step of randomization, however, my tests did not reflect the change in efficiency. 

