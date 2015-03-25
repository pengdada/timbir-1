# TIMBIR

Directory structure
> Source_Code				#Contains all the source code
  >> MBIR_4D				#Contains the source code for 4D model-based iterative reconstruction (4D MBIR)
  >> include				#Contains header files with function prototypes for the reconstruction routines
  >> lib				#Contains compiled libraries of the reconstruction routines
  >> reconstruct			#Code to read the data, reconstruct, and write the data.
    >>> basic				#Software front-end to reconstruct data in basic binary format
    >>> real_data			#Software front-end to reconstruct data in HDF format
        >>>> APS_Data_Format		#Reconstruct data in HDF format primarily used at APS (in Argonne national lab)
        >>>> Standard_Data_Format	#Reconstruct data in a standard HDF format 
    >>> sim_data			#Reconstruct simulated data (NOT FUNCTIONAL YET)

Software Dependencies
- MPI compiler (Intel or Open MPI) 
- OpenMP
- make utility

Compiling the code

1. Compile the MBIR algorithm code in ./Source_Code/MBIR_4D.
   For more info, read the README in ./Source_Code/MBIR_4D.
	> cd ./Source_Code/MBIR_4D
	> make	#Generates library files in ./Source_Code/lib

2. Run the reconstruction algorithm 
	a. If the input data format is standard binary, run the code in ./Source_Code/reconstruct/basic.
	   For more info on data format and running the code, read the README in ./Source_Code/reconstruct/basic.
		> cd ./Source_Code/reconstruct/basic
		> make #Generates executables in the same folder
	b. If the input data is in HDF format used at APS, run the code in ./Source_Code/reconstruct/read_data/APS_Data_Format
	   For more info on data format and running the code, read the README in ./Source_Code/reconstruct/read_data/APS_Data_Format
		> cd ./Source_Code/reconstruct/real_data/APS_Data_Format
		> make #Generates executables in the same folder
	c. If the input data is in standard HDF format, run the code in ./Source_Code/reconstruct/read_data/Standard_Data_Format
	   For more info on data format and running the code, read the README in ./Source_Code/reconstruct/read_data/Standard_Data_Format
		> cd ./Source_Code/reconstruct/real_data/Standard_Data_Format
		> make #Generates executables in the same folder
