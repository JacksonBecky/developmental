
LENS commands for the modelling in 'Late maturation of executive control promotes conceptual development'

To train the model until the training criterion and test the final representations, with control from the start -

#source necessary functions - add folder paths to files as necessary
source my_procs.tcl

#to load the model with control from the start and train until criterion
source CON_TO_FULL_NETWORK_basic_model_changes_CONTROL_FROM_START.in

#record the activation in all units after learning - give folder name before filename and number files for different runs of a model if don't want to overwrite
testAllActs allActs_1.txt {m1rep m2rep m3rep m1m2 m2m1 m1m3 m3m1 m2m3 m3m2 atl}

#delete all info before run another model
deleteNet hier
deleteExampleSets test
deleteExampleSets train


To train the model until the training criterion and test the final representations, with control after a delay  -

#source necessary functions
source my_procs.tcl

#to load the model without control and train for 1000 epochs
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_1k.in
#or 2000 epochs
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_2k.in
#or 3000 epochs
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_3k.in
#or 4000 epochs
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_4k.in
#or 5000 epochs
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_5k.in


# commands to add control gradually over training with a logistic protocol
source gradually_changing_to_control.in
#or with a linear protocol
#source gradually_changing_to_control_LINEAR.in

#record the activation in all units after learning - give folder name before filename and number files for different runs of a model if don't want to overwrite
testAllActs allActs_1.txt {m1rep m2rep m3rep m1m2 m2m1 m1m3 m3m1 m2m3 m3m2 atl}

#delete all info before run another model
deleteNet hier
deleteExampleSets test
deleteExampleSets train


To train the model and record the training time -

#source necessary functions
source my_procs.tcl

#load the model without control and train for 1000 epochs (vary training time when control starts as above)
source CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_1k.in

#commands to add control gradually over training with a logistic protocol (remove if assessing control from start)
source gradually_changing_to_control.in

#save the number of epochs taken to hit the training criterion - give folder name before filename if don't want to overwrite
saveTrainingTime training_time.txt

#delete all info before run another model
deleteNet hier
deleteExampleSets test
deleteExampleSets train


To vary the location of the connections from control, comment out unwanted connections in the .in file where the model is loaded (e.g., CON_TO_FULL_NETWORK_basic_model_changes_CONTROL_FROM_START.in, CON_TO_FULL_NETWORK_basic_model_changes_GRADUAL_CONTROL_1k.in)
Further instruction is given in CON_TO_FULL_NETWORK_basic_model_changes_CONTROL_FROM_START.in




