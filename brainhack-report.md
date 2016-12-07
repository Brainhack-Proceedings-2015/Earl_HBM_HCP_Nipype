---
event: '2015 OHBM Hackathon (HI)'

title:  'Human Connectome Project Minimal Preprocessing Pipelines to Nipype'

author:

- initials: EE
  surname: Earl
  firstname: Eric
  email: earl@ohsu.edu
  affiliation: aff1
  corref: aff1

- initials: DD 
  surname: Demeter
  firstname: Damion V.
  email: demeter@ohsu.edu
  affiliation: aff1

- initials: KM
  surname: Mills
  firstname: Kate
  email: millska@ohsu.edu
  affiliation: aff1

- initials: GM
  surname: Mihai
  firstname: Glad
  email: paulglad.mihai@uni-greifswald.de
  affiliation: aff2
  
- initials: GM
  surname: Ruzic
  firstname: Luka
  email: luka.ruzic@duke.edu
  affiliation: aff3  
  
- initials: NK
  surname: Ketz
  firstname: Nick
  email: nick.ketz@gmail.com
  affiliation: aff4  

- initials: AR
  surname: Reineberg
  firstname: Andrew
  email: andrew.reineberg@colorado.edu
  affiliation: aff4
  
- initials: MR
  surname: Reddan
  firstname: Marianne C.
  email: marianne.reddan@colorado.edu
  affiliation: aff4
  
- initials: ALG
  surname: Goddings
  firstname: Anne-Lise
  email: algoddings@doctors.org.uk
  affiliation: aff5
  
- initials: JGC
  surname: Gonzalez-Castillo
  firstname: Javier
  email: javier.gonzalez-castillo@nih.gov
  affiliation: aff6

- initials: KJG
  surname: Gorgolewski
  firstname: Krzysztof J.
  email: chrisgor@stanford.edu
  affiliation: aff7

affiliations: 

- id: aff1
  orgname: 'Oregon Health & Science University'
  street: 3181 SW Sam Jackson Park Road
  postcode: 97239
  city: Portland
  state: Oregon
  country: USA
  
- id: aff2
  orgname: 'University of Greifswald'
  street: Domstraße 11
  postcode: 17489
  city: Greifswald
  country: Germany

- id: aff3
  orgname: 'Duke Institute for Brain Sciences'
  street: 308 Research Drive, LSRC M051
  postcode: 27708
  city: Durham
  State: North Carolina
  country: USA

- id: aff4
  orgname: 'Department of Psychology and Neuroscience, Unviersity of Colorado'
  street: Muenzinger D244, 345 UCB
  postcode: 80309
  city: Boulder
  State: Colorado
  country: USA  

- id: aff5
  orgname: 'Institute of Cognitive Neuroscience, University College London'
  street: 17 Queen Square
  postcode: WC1N 3AR
  city: London
  country: United Kingdom 
  
- id: aff6
  orgname: 'Section on Functional Imaging Methods, Laboratory of Brain and Cognition, National Institute of Mental Health'
  street: Building 10, Room 1D80, 10 Center Dr. MSC 1148
  postcode: 20892
  city: Bethedsa
  state: Maryland
  country: USA
  
- id: aff7
  orgname: 'Department of Psychology, Stanford University'
  street: Jordan Hall, Building 420, 450 Serra Mall
  postcode: 94305
  city: Stanford
  state: California
  country: USA
  
url: https://github.com/ericearl/hcp2nipype-hack2015/

coi: None

acknow: The authors would like to thank the organizers and attendees of the 2015 OHBM Hackathon.

contrib: EE wrote the report, EE and all other authors wrote the software.
  
bibliography: brainhack-report

gigascience-ref: \href{http://gigadb.org/dataset/100223}{doi:10.5524/100223}
...

#Introduction
The goal was to convert the Human Connectome Project (HCP) Minimal Preprocessing Pipelines into Nipype code.

The HCP minimal preprocessing pipelines \cite{Glasser2013} represent a significant advance in image processing pipelines in our time. They provide preprocessed volume and surface data in native and atlas space, for both functional and structural data. Nipype is an open source neuroimaging project for designing imaging pipelines which has been around since 2011 and provides many excellent features for provenance and reliability of processing pipelines \cite{Gorgolewski2011}. Together, these two pieces of software would allow for a more robust, more flexible synergy of pipeline design and operability.

#Approach
The first goal was to train the would-be Nipype developers on the Nipype python standards for writing and running interfaces.  Once trained, the plan was to implement the HCP scripts into Nipype interfaces from the top-level inward to the sub-level scripts.  The secondary goal was to make these sub-level scripts more flexible and require less specific scans to run the pipelines. The collection of nine ultimate pipelines to implement were with or without T1s or T2s and with or without Fieldmap or Reverse-Phase-Encode EPIs as seen in Table \ref{pipetable}.

\begin{table*}[t!]
\caption{\label{pipetable}Nine pipelines to be implemented.}
\begin{tabular}{l l l l l}
 \hline\noalign{\smallskip}
  EPI & T1 & T2 & Diffusion Field Map & Reverse Phase Encode EPI \\
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
Conceptually these goals sounded reasonable enough to do all HCP scripts at once during the hackathon, but the learning and additional setup time was not accounted for, so the scope of the project was too big for two days of on and off coding, even among our eleven developers.  Distributing Nipype knowledge from two experts to nine novices over two days was not an easy beginning task, but most of the novices had gained knowledge of Nipype usage by the end of the hackathon.  Some work began during the hackathon converting HCP scripts into Nipype pipelines, however not much progress was made due to the unanticipated large scope of work.  The second day, an epiphany came about that the original goal, as stated, would have only involved making five top-level wrappers for the five HCP top-level scripts.  This also slowed some progress.  The secondary goal of generalizing the HCP scripts was discussed, but not thoroughly explored or documented.  There has only been some progress in generalization I am aware of in the Damien Fair, PA-C, PhD, Neuroimaging Lab at OHSU.  This turnout of developers during an open hackathon is encouraging and demonstrates the importance of trying to fuse these two systems (Nipype and the HCP scripts) to work together.  Work on the repository halted after the hackathon, but the team is still available.

# Conclusions
More work is needed to truly contribute back to the HCP Pipelines\footnote{\url{https://github.com/Washington-University/Pipelines}}.  The greatest achievement of the hackathon project was forming a collaborative team of interested Nipype developers who were trained and are ready to continue collaborating across seven institutions.  Future work will continue trying to achieve the original goals as stated, but may need an organizer to hold the team accountable to deadlines.  To get involved with this project, please contact Eric Earl, earl@ohsu.edu.
