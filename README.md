The two components communicate with each other through a TCP connection managed by aiortc. Instead of using multiple channels within one TCP connection, I opted to utilize two separate ports. This decision was made because transferring an image is significantly larger than the tuples (circle centers) that would have been sent over the other channel. 

During testing, I encountered some challenges with aiortc. The library's documentation was limited, and there were few examples available. Additionally, it wasn't widely used in the greater community.

For the client's Circle Detection, I employed Hough Circles. I derived initial values from the paper by Yuen et al. and further fine-tuned them through manual testing. I also set a min and max radius based on the prior knowledge that the server would construct a circle within those bounds.

To see the ball bouncing around, run 'python test_theballapp.py'. The 'view_ball()' method is called by the main method.

To run tests, use 'pytest filename'. There are unit tests for the server, and a comprehensive integration test is available, excluding the aiortc-related functions.
