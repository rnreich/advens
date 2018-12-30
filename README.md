## Recursive-symmetric adversarial ensemble learning
### Unsafe, autonomous self-aware generic super artificial intelligence

![Recursive-symmetric adversarial ensemble learning - Unsafe, autonomous self-aware generic super artificial intelligence](http://i.hmp.me/m/1ca868a0f5f3c1f6d853517d658a8ca5.png)

**Usage (tuned version): python3 run_mvproj.py**

- Multivariate arbitrary projector flags
- Optimized hyperparameters
- Intuitive learning - the network learns only from its own reactions to the input data without being exposed to it
- Exploiting the training cycle
- Real-time negotiator cycle improved
- Better monitoring

Please read all comments. Training is slow before the first save interval. The script is set to use only 1% of the data, so it has to be run at least 100 times in order to achieve respectful results.


**Usage (basic tutorial): python3 load.py**

An array of symmetric, extended adversarial autoencoders. Symmetric means that the length of all latent spaces combined together equals the input size of one autoencoder structure (synapse). So that the entire network's latent space map could be encoded into one single latent space of one unit. The projector and the pretender (a.k.a discriminator & generator) train the memory encoder and the operator to receive and transmit knowledge to and from other synapses. The operator tries to output the correct outputs for the inputs.

When receiving an input, the negotiator (executed code - not a neural network) selects the unit that has the lowest memory decoding error (proof of understanding) and performs the following sequence of operations:


1. Merge latent vectors from all synapses to one latent map

2. Select target synapse by the lowest memory decoding error of the train_x input (prediction only, no fitting)

3. Before any fitting, get predictions from operator. lc_pred proves that the synapse can predict the same result from the latent map without ever training on latent maps directly. It's also possible to fit the network ONLY on the latent maps. Just change lines 141-146 to:

        # STAGE 2 - animate pretender
        synapses[target_synapse][COMP_PRET].fit(x=biglatent, y=[[float(1)]], epochs=EPOCHS, batch_size=1, verbose=0)
        # STAGE 3 - train memory
        synapses[target_synapse][COMP_MEM].fit(x=biglatent, y=biglatent, epochs=EPOCHS, batch_size=1, verbose=0)
        # STAGE 4 - train operator
        synapses[target_synapse][COMP_OP].fit(x=biglatent, y=train_y, epochs=EPOCHS, batch_size=1, verbose=0)

**This is interesting because the network can learn without actually training on any of the input data, only on its own reactions to that data!**

It's slightly better to train the memory first, see tuned version.

4. Encode the train_x input and the latent map itself

5. Train projector

6. Animate pretender

7. Train memory

8. Train operator


Note: Activation functions and other hyper-parameters may be adjusted before using this kernel.

--------------------------------------------------------------------------------

Coded for kaggle's microsoft malware prediction contest:

https://www.kaggle.com/rnreich/recursive-symmetric-adversarial-ensemble-unsafe
