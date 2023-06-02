Inside the directory, create the following folders:

  mkdir hyperparameters_tuning hyperparameters_tuning/GCN hyperparameters_tuning/GCN_hyperTuning
  mkdir results results/GCN results/GCN_Deep

Install the requirements.

To reproduce the result in Cornell with the best hyperparameters in Table 1 execute:

  python main.py --verbose --lr 0.0105 --weight_decay 0.001 --hidden_units 16 --n_layers_set 2 --dropout 0.385 --JostLiuCurvature_Online --pA 0.6651 --pD 0.9863 --alpha 0.1741 --dataset Cornell --GNN SGC

To run a hyperparameters random search with SJLR in the GPU ID 0 in the Cornell dataset, execute:

  python random_search_hyperparameters.py --gpu_number 0 --JostLiuCurvature_Online --dataset Cornell --GNN SGC

To compute the test result with the best results from the validation set:

  python compute_test_accuracy.py --gpu_number 0 --JostLiuCurvature_Online --dataset Cornell --GNN SGC

