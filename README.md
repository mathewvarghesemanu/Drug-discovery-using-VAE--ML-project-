#By- Mathew Varghese
# Drug discovery using VAE (ML-project)
 Using ZINC data base to generate new SMILES strings

Data was downloaded from the ZINC database(https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1360656/) . It had more than 4 lakh drugs data. I took only 35000 drugs for training the VAE. Training was done in google collab. Also the drugs were limited to 35000 as google collab was running out of 25 GB ram while running the training part.
Since drugs had variable lengths, I padded them to 120 characters for ease of handling. Unique characters are taken from the SMILES representation. Using these characters, the drugs were one hot encoded for better handling by VAE.
The Encoder and Decoder was specified along with a VAE class. Also the loss functions were defined and the model was trained for 100 epochs.
Then the decoder was used to extract some drugs from the latent space. It was converted to the onehot encoded form, which was later decoded to 0 to 52 characters form. Another function decoded it to the SMILES format, which was used to print 5 new drugs.
On the first glance, the generated molecules might not comply with the SMILES representation, but it is generated using the VAE. So, with some tuning to set some rules and validating using the database of known molecules, this code can be used to generate real molecules for drug discovery.
