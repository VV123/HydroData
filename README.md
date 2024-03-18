# HydroData

## Data Description as A Graph

`Node`: junction (e.g., v_i=1), hydrological data are represented as node features. 

`Edge`: conduit (e.g., <v_i, v_j>), material, slope, and other static edge features. 


## Files and Field Descriptions

# WW01_v3 Dataset Documentation

## Files Description

### WW01_v3.xls

This Excel file contains two sheets of Node dynamic features related to a wastewater network.

#### Depth Sheet - Time Series Data

- **IDs**: Unique identifiers for the nodes in the wastewater network.
- **Date/Time**: Timestamp for each observation of depth measurements.
- **Depth Columns**: Provide the depth of water at that node in feet, with the column name matching the node ID.

#### Inflow Sheet - Node Inflow Data

- **Name**: Unique identifiers or names for nodes where inflow data is measured.
- **X-Coordinate**: Horizontal position of the node on a map.
- **Y-Coordinate**: Vertical position of the node on a map.
- **Tag**: Additional classification or tagging of the node.
- **Inflows**: Whether the node has inflow.
- **Treatment**: Whether the node is associated with a treatment process.
- **Invert Elev. (ft)**: Elevation of the invert in feet.
- **Rim Elev. (ft)**: Elevation of the rim in feet.
- **Depth (ft)**: Depth of flow at the node in feet.
- **Time Series**: Reference to a .dat file with time series inflow data for the node.

### WW01.png

This image represents a schematic map of a wastewater network, showing interconnections and pathways between nodes and conduits.

### WW01_node.csv - Node Static Feature File

Contains static features for nodes in the wastewater network with the following columns:

- **Node ID**: Unique identifier for each node in the wastewater network.
- **X-Coordinate**: The X-axis coordinate of the node's location, possibly in a specific map projection.
- **Y-Coordinate**: The Y-axis coordinate of the node's location.
- **Tag**: A label or marker used for categorization or additional information about the node.
- **Inflows**: Indicates if there is water entering the system at this node.
- **Treatment**: Shows whether this node is associated with any treatment processes.
- **Invert Elev. (ft)**: The elevation of the lowest point of the interior of the node, in feet.
- **Rim Elev. (ft)**: The elevation of the top edge of the node structure, in feet.
- **Depth (ft)**: The current or initial depth of water at the node, in feet.
- **Initial Depth (ft)**: The depth of water at the beginning of a simulation or time period, in feet.
- **Surcharge Depth (ft)**: The depth of water above the rim elevation during surcharge conditions, in feet.
- **Ponded Area (ft²)**: Area of water ponding at the node during surcharge, in square feet.
- **Baseline (cfs)**: Baseline flow rate at the node, in cubic feet per second.
- **Baseline Pattern**: Reference to a pattern or typical behavior of baseline flow at the node.
- **Scale Factor**: A multiplier applied to scale the baseline or pattern values.
- **Average Value (cfs)**: The average flow rate at the node, in cubic feet per second.
- **Time Pattern 1 - 4**: References to time-based patterns that affect the node's inflow or system behavior.
- **Hydrograph**: A graphical representation of the flow rate versus time at this node.
- **Sewershed Area (ac)**: The area of the sewer system's watershed draining to this node, in acres.
- **Avg. Depth (ft)**: The average depth of water at the node over a specified period, in feet.
- **Max. Depth (ft)**: The maximum depth of water that occurs at the node, in feet.
- **Max. HGL (ft)**: Maximum hydraulic grade line elevation at the node, in feet.
- **Time Max. HGL (M/D/Y)**: Date and time when the maximum HGL occurs.
- **Rep. Max. Depth (ft)**: Representative maximum depth at the node, in feet.
- **Max. Lat. Inflow (cfs)**: Maximum lateral inflow rate into the node, in cubic feet per second.
- **Max. Total Inflow (cfs)**: Maximum total inflow rate into the node, including lateral and upstream sources, in cubic feet per second.
- **Total Lat. Inflow (MG)**: Total lateral inflow volume into the node, in million gallons.
- **Total inflow (MG)**: Total inflow volume into the node, in million gallons.
- **Flow Error (%)**: Percentage of error in the flow measurements or calculations.
- **Hours Surcharged (h)**: Total number of hours the node is surcharged.
- **Max. Surcharge (ft)**: Maximum height of surcharge at the node, in feet.
- **Min. Freeboard (ft)**: Minimum vertical distance between the water surface and the top edge of the node structure, in feet.
- **Hours Flooded (h)**: Total number of hours the node experiences flooding.
- **Max. Flood Rate (cfs)**: Maximum rate of flooding at the node, in cubic feet per second.
- **Total Flood Vol. (MG)**: Total volume of floodwater at the node, in million gallons.
- **Max. Pond Vol. (1000 ft³)**: Maximum volume of ponding at the node during surcharge, in thousands of cubic feet.
- **Contributing Area (ac)**: Area that contributes runoff to the node, in acres.
- **Contributing Imp. Area (ac)**: Impervious area within the contributing region, in acres.
- **Max. Unit Flow (cfs/ac)**: Maximum flow rate per unit area contributing to the node, in cubic feet per second per acre.
- **GIS_LENGTH (m)**: Length of the node feature as represented in a Geographic Information System, in meters.
- **GIS_AREA (m²)**: Area of the node feature as represented in GIS, in square meters.
- **GIS_PARTS**: The number of parts or components that make up the node feature in the GIS system.

### WW01_pipe.csv - Edge Static Feature File

Describes the static features of the edges in the wastewater network with the following columns:

- **Name**: Unique identifier or name for the pipeline segment or system component.
- **Inlet Node**: Identification number or code for the inlet node, marking where flow enters the segment.
- **Outlet Node**: Identification number or code for the outlet node, marking where flow exits the segment.
- **Tag**: An optional label or tag for additional categorization or notes about the segment.
- **Length (ft)**: Length of the pipeline segment in feet.
- **Roughness**: A measure of the internal surface roughness of the pipe, influencing flow resistance and hydraulic capacity.
- **Inlet Offset (ft)**: Vertical offset at the inlet in feet, possibly indicating elevation differences between the inlet and ground surface or the pipeline itself.
- **Outlet Offset (ft)**: Vertical offset at the outlet in feet, similar to inlet offset but for the outlet end.
- **Initial Flow (cfs)**: The flow rate in cubic feet per second entering the segment under initial or design conditions.
- **Flow Limit (cfs)**: Maximum allowable flow rate in cubic feet per second to prevent overflow or system stress.
- **Entry Loss Coeff.**: Coefficient quantifying energy or head loss at the entry to the segment due to friction and turbulence.
- **Exit Loss Coeff.**: Coefficient quantifying energy or head loss at the exit of the segment.
- **Avg. Loss Coeff.**: Average coefficient for energy or head loss across the entire segment.
- **Seepage Rate (in/hr)**: Rate at which water may seep through the pipe walls or joints, in inches per hour.
- **Flap Gate**: Indicates whether a flap gate is installed to prevent backflow into the segment.
- **Cross-Section**: Type or shape of the pipe's cross-sectional area (e.g., circular, rectangular).
- **Geom1 (ft)**: Primary geometric dimension of the cross-section (e.g., diameter for a circular pipe), in feet.
- **Geom2 (ft)**: Secondary geometric dimension (e.g., width for a rectangular pipe), in feet.
- **Geom3**: Third geometric dimension or parameter, specific to the cross-section shape.
- **Geom4**: Fourth geometric dimension or parameter, specific to the cross-section shape.
- **Barrels**: Number of parallel pipes or barrels in the segment.
- **Transect**: Reference to a detailed cross-section used for complex or non-standard shapes.
- **Shape Curve**: Curve number or identifier for predefined cross-sectional shapes or profiles.
- **Culvert Code**: Code or identifier for culvert configurations or standards.
- **Control Rules**: Reference to operational rules or controls applied to the flow through the segment.
- **Street**: Name of the street or location where the segment is situated.
- **Inlets**: Number of inlets feeding into the segment.
- **Slope (ft/ft)**: Slope of the segment in feet per foot, affecting flow velocity and capacity.
- **Max. |Flow| (cfs)**: Maximum observed absolute flow rate in cubic feet per second.
- **Time Max. Flow (M/D/Y)**: Date of the maximum observed flow.
- **Max. |Velocity| (ft/s)**: Maximum observed absolute velocity of flow through the segment in feet per second.
- **Max/Full Flow**: Ratio of maximum flow to the flow at full capacity.
- **Max/Full Depth**: Ratio of maximum depth of flow to the depth at full capacity.
- **Max. Volume (ft³)**: Maximum volume of flow in cubic feet.
- **Inlet Structure**: Type or description of the inlet structure.
- **Capture Node**: Node or location where flow is captured or diverted.
- **Number of Inlets**: Total number of inlet points feeding the segment.
- **Percent Clogged**: Percentage of the segment's capacity reduced due to clogging.
- **Flow Restriction (cfs)**: Flow rate in cubic feet per second beyond which the segment becomes restricted.
- **Depression Height (ft)**: Height of any depressions or sags in the segment, in feet.
- **Depression Width (ft)**: Width of any depressions or sags in the segment, in feet.
- **Inlet Placement**: Describes the placement or positioning of inlets relative to the segment.
- **Full Both Ends (h)**: Hours of operation with both ends full.
- **Full Upstream (h)**: Hours of operation with the upstream end full.
- **Full Downstream (h)**: Hours of operation with the downstream end full.
- **Above Full Normal (h)**: Hours of operation above normal full capacity.
- **Capacity Limited (h)**: Hours during which the segment's capacity is limited.
- **Length Factor (fraction)**: Fractional factor representing the effect of segment length on performance.
- **Dry (fraction)**: Fraction of time the segment is dry or not conveying flow.
- **Subcritical (fraction)**: Fraction of time flow is subcritical.
- **Supercritical (fraction)**: Fraction of time flow is supercritical.
- **Normal Limited (fraction)**: Fraction of time the segment operates under normal, limited conditions.
- **Inlet Control (fraction)**: Fraction of time inlet control affects the segment's performance.
- **Maximum Spread (ft)**: Maximum width of flow spread at the surface, in feet.
- **Maximum Depth (ft)**: Maximum depth of flow, in feet.
- **Inlet Location**: Specifies the location of the inlet relative to the segment.
- **Peak Flow Capture (%)**: Percentage of peak flow captured by the system.
- **Average Capture (%)**: Average percentage of flow captured by the system over time.
- **Bypass Frequency (%)**: Frequency at which flow bypasses the intended capture or treatment.
- **Back Flow Frequency (%)**: Frequency of flow reversal, indicating backflow conditions.
- **Peak Capture/Inlet**: Peak flow rate captured per inlet.
- **Peak Bypass Flow**: Peak flow rate that bypasses the system.
- **Max. Spread (ft)**: Maximum width of flow spread on the surface, in feet.
- **Contributing Area (ac)**: Area contributing flow to the segment, in acres.
- **Contributing Imp. Area (ac)**: Impervious area within the contributing area, in acres.
- **Max. Unit Flow (cfs/ac)**: Maximum flow rate per acre of contributing area.
- **GIS_LENGTH (m)**: Length of the segment as measured in GIS, in meters.
- **GIS_AREA (m²)**: Area covered or represented by the segment in GIS, in square meters.
- **GIS_PARTS**: Number of discrete parts or segments that the feature is divided into within the GIS system.
