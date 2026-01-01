```#include<stdio.h>
#include<stdlib.h>
#include<math.h>
#define numinputs 2
#define numhiddennodes 2
#define numoutputs 1
#define numtrainingSets 4
double sigmoid(double x){ return 1 /(1+exp(-x));}
doubledsigmoid(double x){ return x * (1-x);}
doubleinit_weights() { return((double)rand()) / ((double)RAND_MAX);}
void shuffle(int *array,size_t n){
	if(n>1)
    {
size_ti;   //inti,j;
	for(i=0;i<n-1;i++){
		size_t j =i+rand() / (RAND_MAX / (n - i) + 1);
		int t = array[j];
		array[j] = array[i];
		array[i] = t;
	}
    }
}
int main(void)
{
	const double lr = 0.1f;
	doublehiddenlayer[numhiddennodes];
	doubleoutputlayer[numoutputs];
	doublehiddenlayerbias[numhiddennodes];
	doubleoutputlayerbias[numoutputs];
	doublehiddenweights[numinputs][numhiddennodes];
	doubleoutputweights[numhiddennodes][numoutputs];
	
	
	double training_inputs[numtrainingSets][numinputs]={{0.0f,0.0f},{1.0f,0.0f},{0.0f,1.0f},{1.0f,1.0f}};
	double training_outputs[numtrainingSets][numoutputs]={{0.0f},{1.0f},{0.0f},{1.0f}};
	for(inti=0;i<numinputs;i++){
		for(int j=0;i<numhiddennodes;j++){
			hiddenweights[i][j] = init_weights();
		}
	}
	
	for(inti=0;i<numhiddennodes;i++){
		for(int j=0;i<numoutputs;j++){
			outputweights[i][j] = init_weights();
		}
	}
	for(inti=0;i<numoutputs;i++){
		outputlayerbias[i]= init_weights();
	}
	inttrainingsetorder[] = {0,1,2,3};
	intnumberofepochs = 1000;
	// train the neural network for a number of epochs
	for (int epoch = 0;epoch<numberofepochs;epoch++){
		shuffle(trainingsetorder,numtrainingSets);
		for(int x =0;x<numtrainingSets;x++){
			inti = trainingsetorder[x];
			//forward pass
			//compute hidden layer activation
			for(int j = 0;j<numhiddennodes;j++){
				double activation = hiddenlayerbias[j];
				for(int k=0;k<numinputs;k++ ){
					activation += training_inputs[i][k] * hiddenweights[k][j];
		}
hiddenlayer[j] = sigmoid(activation);
		}
			//compute output layer activation
			for(int j = 0;j<numoutputs;j++){
				double activation = outputlayerbias[j];
				for(int k=0;k<numhiddennodes;k++ ){
					activation += hiddenlayer[k] * outputweights[k][j];
			}
			outputlayer[j] = sigmoid(activation);
			}
			printf("Input : %g%g  Output : %g     Predicted Output : %g     error : %g\n",
			        training_inputs[i][0],training_inputs[i][1],training_outputs[i][0],outputlayer[0],(training_outputs[i][0]-outputlayer[0]));
			//backpropagation
			//compute change in output weights 
			doubledeltaoutput[numoutputs];
			for(int j = 0;j<numoutputs;j++){
				double error = (training_outputs[i][j] - outputlayer[j]);
				deltaoutput[j] = error * error * dsigmoid(outputlayer[j]);		
			}
			//compute change in hidden weights
			doubledeltahidden[numhiddennodes];
			for(int j=0;j<numhiddennodes;j++){
				double error = 0.0f;
				for(int k=0;k<numoutputs;k++){
					error += deltaoutput[k] * outputweights [j][k];
				}
				deltahidden[j] = error * dsigmoid(hiddenlayer[j]);
			}
			
			//apply change in output weights
			for(int j=0;j<numoutputs;j++){
				outputlayerbias[j] += deltaoutput[j] * lr;
				for(int k = 0; k<numhiddennodes; k++){
					outputweights[k][j] += hiddenlayer[k] * deltaoutput[j] * lr;
				}
			}
			
			//apply change in hidden weights
			for(int j=0;j<numhiddennodes;j++){
				hiddenlayerbias[j] += deltahidden[j] * lr;
				for(int k = 0; k<numhiddennodes; k++){
					hiddenweights[k][j] += training_inputs[i][k] * deltaoutput[j] * lr;
				}
			}
		}
	}
//print final weights after done training
		fputs("final hidden weights \n",stdout);
			for(int j=0;j<numhiddennodes;j++){
				fputs("[",stdout);
				for(int k=0 ;k<numinputs; k++){
					printf("%f",hiddenweights[k][j]);
				}
				fputs("]",stdout);
			}
			fputs("]\nfinal hidden biases \n[",stdout);
			for(int j=0;j<numhiddennodes;j++){
				printf("%f",hiddenlayerbias[j]);
			}
			fputs("final output weights \n",stdout);
			for(int j=0;j<numoutputs;j++){
				fputs("[",stdout);
				for(int k=0 ;k<numhiddennodes; k++){
					printf("%f",outputweights[k][j]);}
				fputs("]",stdout);
			}
			
			fputs("]\nfinal output biases \n[",stdout);
			for(int j=0;j<numoutputs;j++){
				printf("%f",outputlayerbias[j]);
			}
			
			fputs("] \n ",stdout);
			return 0;
}# MLP–Wavelet Neural Approximator on STM32

This project implements a neural network–based function approximator using
Multilayer Perceptron (MLP) and Wavelet Neural Network (WNN) on an STM32
microcontroller.

## Features
- MLP and Wavelet Neural Network implementation
- MATLAB-based training and analysis
- Embedded deployment on STM32 using CubeIDE
- Real-time signal approximation
- Optimized for memory and power constraints

## Tools & Technologies
- STM32 Nucleo (STM32F401RE)
- STM32 CubeIDE
- MATLAB
- C / C++

## Applications
- Biomedical signal processing (ECG/EEG)
- Embedded signal approximation
- Low-power edge intelligence
