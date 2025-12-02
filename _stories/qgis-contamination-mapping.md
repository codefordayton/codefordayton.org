---
title: "Using QGIS to Identify Homes Affected by Contamination Vapors"
summary: "Community group mapped EPA vapor contamination data to generate actionable address lists for door-to-door outreach"
tools: [qgis, openstreetmap, gis, python]
problem_type: [environmental, geospatial, community-outreach]
skill_level: intermediate
date: 2023-05-03
project_link: "https://github.com/codefordayton/vapor-mapping"
contact: "team@codefordayton.org"
resources:
  - title: "QGIS Official Website"
    url: "https://qgis.org/"
  - title: "Montgomery County Parcel Data"
    url: "https://www.mcohio.org/631/GIS-Downloads"
  - title: "EPA Contamination Map"
    url: "https://semspub.epa.gov/work/05/968770.pdf"
  - title: "Original Blog Post"
    url: "/2023/05/03/qgis-plume.html"
---

## Situation

A community organization in Dayton was facing a significant environmental health challenge. They had a Superfund contamination site in their neighborhood where toxic vapors could seep into homes, requiring testing and potential installation of vapor abatement systems. 

The Environmental Protection Agency (EPA) had provided a map showing the contamination plume and eligible areas for testing, but it was only available as a grainy PDF map with geographic boundaries. The community group needed actual street addresses to conduct effective door-to-door outreach to inform residents about testing availability and health risks.

**The Challenge**: Convert a vague PDF boundary map into a concrete list of street addresses for targeted community outreach.

## Task

Our goal was to:
1. Accurately map the EPA's contamination boundary onto current parcel data
2. Identify all residential properties within the affected area
3. Generate a list of specific addresses for door-to-door outreach
4. Provide the community group with actionable data they could use immediately

The project needed to be completed quickly and accurately, as residents' health was potentially at risk, and the community group had limited time and resources for their outreach campaign.

## Action

We used QGIS (Quantum Geographic Information System), an open-source mapping tool, to solve this geospatial puzzle. Here's the step-by-step process we followed:

### 1. Project Setup
- Created a new empty QGIS project
- Added OpenStreetMap as a basemap for geographic reference
- Downloaded and imported Montgomery County's parcel shapefile containing property boundaries and addresses

### 2. Map Georeferencing
The most challenging step was accurately positioning the EPA's PDF map onto our coordinate system:
- Used QGIS's built-in Georeferencer tool
- Identified 8+ matching reference points between the PDF and OpenStreetMap (building corners, road intersections)
- Iteratively enabled/disabled reference points to minimize error
- Achieved less than 10 pixels of error around the boundary
- Verified accuracy by toggling the georeferenced image on/off to check alignment

### 3. Boundary Digitization
- Created a new shapefile layer for the contamination boundary
- Used the "Add Polygon Feature" tool to manually trace the plume boundary from the georeferenced PDF
- Carefully followed the EPA's defined contamination zone

### 4. Spatial Analysis
- Used QGIS's "Select by Location" tool to identify all parcels that intersected with the contamination boundary
- This automatically selected all properties within or touching the affected area
- Verified the selection visually on the map

### 5. Data Export
- Exported the selected parcels as a CSV file containing addresses and property details
- Cleaned and formatted the data for easy use by the community organization

### Tools and Data Sources Used:
- **QGIS**: Primary mapping and analysis software
- **OpenStreetMap**: Basemap for georeferencing
- **Montgomery County Parcel Data**: Property boundaries and addresses
- **EPA PDF Map**: Contamination boundary source

## Result

The project was highly successful and had immediate community impact:

### Immediate Outcomes:
- **Precise Address List**: Generated a complete list of residential addresses within the EPA contamination zone
- **Actionable Data**: Community group could immediately begin targeted door-to-door outreach
- **Time Savings**: Eliminated hours of manual address research and guesswork
- **Accuracy**: Ensured no at-risk homes were missed in the outreach campaign

### Technical Learning:
- **QGIS Proficiency**: Team gained hands-on experience with professional GIS software
- **Georeferencing Skills**: Learned techniques for aligning different map projections and data sources
- **Spatial Analysis**: Developed capability for location-based data analysis
- **Data Integration**: Successfully combined federal, county, and community data sources

### Community Impact:
- **Health Protection**: Enabled targeted outreach to residents who might be exposed to toxic vapors
- **Efficient Resource Use**: Community organization could focus limited volunteer time on affected areas
- **Empowered Advocacy**: Provided concrete data to support environmental justice efforts

### Long-term Value:
- **Replicable Process**: Documented methodology can be used for similar environmental mapping challenges
- **Skill Building**: Added GIS capabilities to our civic tech toolbox
- **Community Partnership**: Strengthened relationship between Code for Dayton and local environmental groups

This project demonstrated how open-source mapping tools can quickly transform hard-to-use government data into actionable community resources. The entire process took just a few hours but enabled weeks of effective community outreach that could directly impact residents' health and safety.

**Key Takeaway**: Sometimes the most impactful civic tech projects aren't building new apps—they're using existing tools to make critical information accessible to the people who need it most.
