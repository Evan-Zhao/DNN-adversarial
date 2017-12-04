# Real-world Accidents Involving ML Systems

(This is a topic in [README.md](../README.md).)

### Self-driving Car

Failures of ML systems on self-driving car tend to cause severe outcomes, so such cases are relatively more exposed and studied. 

The table below summarizes 4 self-driving car accidents with relavant links. Part of the material below was in the paper "DeepTest: Automated Testing of Deep-Neural-Network-driven Autonomous Cars." [[7]](https://arxiv.org/abs/1708.08559). 

|                         | Reported Date  | Cause                                   | Outcome                                  | Comments                                 |
| ----------------------- | -------------- | --------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| Hyundai Competition [1](https://spectrum.ieee.org/cars-that-think/transportation/advanced-cars/japan-competition-shows-weather-still-a-challenge-for-autonomous-cars)    | December, 2014 | Rain fall                               | Crashed while testing                    | "The sensors failed to pick up street signs, lane markings, and even pedestrians due to the angle of the car shifting in rain and the direction of the sun" |
| Tesla autopilot mode [1](http://www.businessinsider.com/report-government-closing-tesla-autopilot-fatality-investigation-2017-1), [2](https://www.theverge.com/2016/6/30/12072408/tesla-autopilot-car-crash-death-autonomous-model-s)   | July, 2016     | Image contrast                          | Killed the driver                        | "The camera failed to recognize the white truck against a bright sky" |
| Google self-driving car [official report](https://static.googleusercontent.com/media/www.google.com/zh-CN//selfdrivingcar/files/reports/report-0916.pdf)| February, 2016 | Failed to estimate speed                | Hit a bus while shifting lane            | "The car assumed that the bus would yield when it attempted to merge back into traffic" |
| Uber self-driving car [1](http://www.businessinsider.com/uber-self-driving-car-accident-arizona-police-report-2017-3), [2](http://www.autonews.com/article/20170325/MOBILITY/170329884/uber-suspends-self-driving-car-program-after-arizona-crash)  | Mar, 2017      | Failed to predict other cars' movements | Hit by a left-turning car at intersection | "The self-driving car maintained its speed of 38 mph to cross the intersection in time at the yellow light" |

### Stereotypical and Biased AI

* Crime risk assessor PredPol is biased against blacks: [link](https://mic.com/articles/156286/crime-prediction-tool-pred-pol-only-amplifies-racially-biased-policing-study-shows)

* Microsoft tweeter bot Tay veered into white supremacy: [link](https://motherboard.vice.com/en_us/article/kb7zdw/microsoft-suspends-ai-chatbot-after-it-veers-into-white-supremacy-tay-and-you)

*Note* that, instead of being a fallacy in ML system function, the issues fall in this category are caused by the data; the algorithm works normally as is. Emiel van Miltenburg [[8]](https://arxiv.org/pdf/1605.06083.pdf) extensively studied the Flickr30K dataset, which is commonly used to train and evaluate neural network models that generate image descriptions, and shows that it contains bias and stereotypes. 