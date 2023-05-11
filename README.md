# oscd-edit-check

This OpenSCD core plugin provides an editor that listens for edit events and corrects those in case something is missing.
One such used case are `Remove` actions. Often removing something from the SCL comes with all kind of adoption along the line. Removing an IED for example lead to removing all references pointing to this IED and removing all `LNodeType` typicals that have been exclusevely used by this one IED. 

# Removing 
- `GSEControl` -> (`DataSet`) -> (`ExtRef`) -> (`LGOS/LSVS`)
- `ReportControl` -> (`DataSet`) -> (`ExtRef`)
- `SampledValueControl` -> (`DataSet`) -> (`ExtRef`) -> (`LGOS/LSVS`)
- `DataSet` -> (`ExtRef`) -> (`LGOS/LSVS`)
- `FCDA` -> (`ExtRef`) -> (`LGOS/LSVS`)
- `ExtRef` -> (`LGOS/LSVS`)
- `IED` -> (`LNode`) -> (`ExtRef`) -> (`LGOS/LSVS`) -> (`LNodeType`) -> (`DOType`) -> (`DAType`) -> (`EnumType`) -> (`ConnectedAP`) -> (`SubNetwork`)


# Update
- Substation.name -> (`ConnectivityNode`) -> (`Terminal`)
- VoltageLevel.name -> (`ConnectivityNode`) -> (`Terminal`)
- Bay.name -> (`ConnectivityNode`) -> (`Terminal`)
- GSEControl.name -> (`LGOS`) -> (`ExtRef`)
- SampledValueControl.name -> (`LSVS`) -> (`ExtRef`)
- ReportControl.name -> (`ExtRef`)


# Usage
To use the functionality just add the editor plugins in our OpenSCD core distribution. Edit events bubbling to OpenSCD core are triggering the functionality of this plugin. 
