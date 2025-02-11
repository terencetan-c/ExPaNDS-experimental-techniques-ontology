# Background
The Photon and Neutron Experimental Techniques (PaNET) ontology is a taxonomy of experimental techniques relevant to the Photon and Neutron (PaN) community. It was developed as part of the European Open Science Cloud (EOSC) Photon and Neutron Data Service (ExPaNDS) project.

<img width="520" alt="image" src="https://github.com/user-attachments/assets/402dee87-7214-4dcd-83a6-879b8d698298" />

The Zenodo paper [1] introducing the ontology also discussed some possible future developments. In particular, the authors noted that PaNET v1.0 implies key relationships which could be defined explicitly using object properties.

For example, the class \<photon probe\> refers to PaN techniques defined by photon probes, and not the actual probes themselves. However, \<photon probe\> can be linked to a class representing the actual photon probe using an object property such as (definedByProbe). This new class will be a subclass of a \[Probe\] class, which is itself a subclass of a \[photon and neutron related concepts\] class. Of course, the original \<photon probe\> will have to be renamed to something like \<photon probe_technique\> to avoid confusion, and the new class can be named \[photon probe\].

The use of chevron bracket, i.e. \<\>, will denote a class belonging to \<photon and neutron technique\>. The use of square brackets, i.e. \[\], will denote classes that are PaN-related concepts. The use of regular brackets, i.e. (), will denote object properties.

In addition, the \<photon and neutron technique\> classes in PaNET v1.0 were defined mainly using subclass axioms, i.e. Class A being a subclass of Class B.  However, users of the PaNET ontology have noted that certain subclass relationships are missing from the original ontology. Given that all the subclass axioms/relationships in the original PaNET were added manually, looking for and including missing relationships would be a time-consuming task. The use of object properties and stronger logical statements would allow reasoners to automatically infer relationships, which would be a more robust and versatile approach.

This piece of work aims to add four object properties and the corresponding relevant classes to the ontology, and use those to make stronger logical statements, thereby allowing the reasoner to perform the bulk of the task of creating relationships between the classes of the ontology.

# Methodology

<img width="961" alt="image" src="https://github.com/user-attachments/assets/ba1c25e5-ce67-47fa-990d-6ae4cac90d76" />

## New classes
The \[photon and neutron related concepts\] class is added, with four subclaasses: \[Probe\], \[Process\], \[Functional Dependence\], and \[Purpose\]. Each of these four classes have their own respective corresponding subclasses, such as \[photon probe\] under \[Probe\].

## Object properties
Four object properties are added: (definedByProbe), (definedByProcess), (definedByDependence), and (definedByPurpose). Their domains are all \<photon and neutron technique\>, and their ranges are \[Probe\], \[Process\], \[Functional Dependence\], and \[Purpose\] respectively.

## Redefining the technique classes
As mentioned earlier, the \<photon and neutron technique\> classes in PaNET v1.0 were defined mainly using subclass axioms. In this new version, the classes will be defined using a mixture of object properties, equivalence axioms, and subclass axioms.

### Class-property equivalence
Some \<photon and neutron technique\> classes are defined by their relationships to \[photon and neutron related concepts\] classes via object properties. For example, \<photon probe_technique\> ≡ (definedByProbe) some \[photon probe\].

### Class equivalence
Rather than just being a subclass of another class, many \<photon and neutron technique\> classes are now made equivalent to the intersection of their former parent classes. This represents a much stronger logical statement, which will allow more use of the reasoner's inference capabilities. For example, \<x-ray absorption\> ≡ \<absorption technique\> ∩ \<x-ray probe_technique\>.

### Subclass
In some cases, it is more appropriate to keep the subclass axioms as they are. For example, \<ambient pressure x-ray photoelectron spectroscopy\> ⊆ \<x-ray photoelectron spectroscopy\>.

## Verification


# References
[1] Collins, S. P., da Graça Ramos, S., Iyayi, D., Görzig, H., González Beltrán, A., Ashton, A., Egli, S., & Minotti, C. (2021). ExPaNDS ontologies v1.0. Zenodo. https://doi.org/10.5281/zenodo.4806026
