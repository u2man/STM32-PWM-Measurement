STM32 Frequency and Duty Cycle Measurement


This is the sample code of frequency measurement using STM32 Timer.
The timer will works as input capture, two channel use in this measurement.
Channel 1 will measure the periode (frequency) and channel 2 wil measure duty cycle.

The channel 1, will active in rising edge of the signal, and channel 2 will active in falling edge of the signal.
In first rising transition of the signal, both channel will in reset and start counting.
When falling edges occurs, the channel 2 will rise an interrupt and the capture will save the duty cycle.
And when the next rising edge, channel 1 will capture the periode of the signal.

The frequency will be calculate as Timer Frequency/Channel1 Counter.
And the duty cycle is (Channel 2 Counter/Channel 1 Counter) x 100%.

The minimum frequency that can be measure is (Timer Frequency/Auto-reload Counter), in this program timer frequency is 60 MHz, and the reload counter is 655535 (16 bit).
So the minimum frequency is 915.5 Hz.

What is the max frequnecy?
Check this video
