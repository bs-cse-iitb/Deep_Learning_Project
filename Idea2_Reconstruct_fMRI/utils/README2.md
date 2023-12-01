fMRI 4d data → preprocessed fMRI data 
[borrowed from nsd access]

MSCOCO Image corresponding fMRI preprocessed data {visual cortex-ROI early} (Y)

MSCOCO Images to pretrained encoder of latent diffusion model (ldm) → latent representation z (X)

Divide X_tr, X_te and Y_tr, Y_te by corresponding right mapping of fMRI preprocessed data (Y) and latent representation z (X)
train (X_tr,Y_tr)
test (X_te,Y_te)

comparative study Ridge regression and neural network for reconstruction of fMRI data





python img2feat_encoding_z.py  --imgidx 0 73000 --gpu 0

python make_subjstim_encoding.py --featname init_latent --use_stim each --subject subj01
python make_subjstim_encoding.py --featname init_latent --use_stim ave --subject subj01

python encoding_ridge.py --target z --roi early --subject subj01
python encoding_NN.py --target z --roi early --subject subj01