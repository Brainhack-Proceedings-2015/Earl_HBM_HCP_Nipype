---
event: '2015 OHBM Hackathon (HI)'

title:  'Human Connectome Project to Nipype'

author:

- initials: EE
  surname: Earl
  firstname: Eric
  email: earl@ohsu.edu
  affiliation: aff1
  corref: aff1

affiliations: 

- id: aff1
  orgname: 'Oregan Health & Science University'
  street: 1 club St
  postcode: 90270
  city: Portland
  state: Oregon
  country: USA

url: http://github.com/hcp_nipype/hackathon

coi: None

acknow: The authors would like to thank the organizers and attendees of the 2015 OHBM Hackathon.

contrib: EE wrote the software and the report.
  
bibliography: brainhack-report

gigascience-ref: REFXXX
...

#Introduction
The goal was to convert the Human Connectome Project (HCP) Minimal Preprocessing Pipelines into Nipype code.

The HCP minimal preprocessing pipelines \cite{Glasser2013} represent a significant advance in image processing pipelines in our time. They provide preprocessed volume and surface data in native and atlas space, for both functional and structural data. Nipype is an open source neuroimaging project for designing imaging pipelines which has been around since 2011 and provides many excellent features for provenance and reliability of processing pipelines. Together, these two pieces of software would allow for a more robust, more flexible synergy of pipeline design and operability.

#Approach
The first goal was to train the would-be Nipype developers on the Nipype python standards for writing and running interfaces.  Distributing this knowledge from two experts to nine novices over two days was not an easy beginning task.  Once trained, the plan was to implement the HCP scripts into Nipype interfaces from the top-level inward to the sub-level scripts. The secondary goal was to make these sub-level scripts more flexible and require less specific scans to run the pipelines. The collection of nine ultimate pipelines to implement were with or without T1s or T2s and with or without Fieldmap or Reverse-Phase-Encode EPIs as seen in the below table.

\begin{table*}[t!]
\caption{\label{paramtable}This is the caption for the table.}
\begin{tabular}{l l l l l}
 \hline\noalign{\smallskip}
          EPI & T1 & T2 & Diffusion Field Map & Reverse Phase Encode EPI \\
    \noalign{\smallskip}
    \hline\noalign{\smallskip}
          N & N & N & 1 & 0 \\
		  N & N & 0 & 1 & 0 \\
		  N & 0 & N & 1 & 0 \\
		  N & N & N & 0 & N \\
		  N & N & 0 & 0 & N \\
		  N & 0 & N & 0 & N \\
		  N & N & N & 0 & 0 \\
		  N & N & 0 & 0 & 0 \\
		  N & 0 & N & 0 & 0 \\
  \noalign{\smallskip}\hline
\end{tabular}
\end{table*}


#Results
The scope of the project was too big for two days of on and off coding, even among eleven developers.  However, this turnout of developers during an open hackathon demonstrates the importance of trying to fuse these two systems (Nipype and the HCP pipelines) to work together.


# Conclusions
More work is needed to truly contribute back to the HCP Pipelines (https://github.com/Washington-University/Pipelines), but a collaborative team of interested Nipype developers were trained and are ready to continue collaborating across seven institutions on a vastly beneficial project to all of our work.
