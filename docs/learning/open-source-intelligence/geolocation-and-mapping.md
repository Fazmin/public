# Geolocation and Mapping

## Description

Geolocation and Mapping in OSINT involves extracting and analyzing location-based clues from various sources such as images, videos, and textual data to determine the physical whereabouts of a subject or event. Techniques include examining image metadata like EXIF for GPS coordinates, identifying landmarks or environmental features through visual analysis, and leveraging mapping tools and satellite imagery for cross-referencing and verification. This process is vital for investigations, threat intelligence, and operations requiring spatial context and precise location identification.

## Why This Matters

Geolocation and mapping matter because location-based clues help investigators determine where an event occurred, where a subject is located, or how a threat actor operates in physical space. Images, videos, and online posts often contain hidden or visible details—such as GPS metadata, landmarks, shadows, or environmental cues—that can reveal precise geographic information. By analyzing these clues and verifying them with mapping tools or satellite imagery, investigators improve situational awareness, validate events, and support accurate intelligence assessments.

Operations rely on accurate spatial information to assess risks, protect campus assets, and understand where incidents or threats originate. Geolocation and mapping help operational teams:
- Determine the physical location of suspicious online activity or potential threats by analyzing shared images, videos, or posts
- Verify whether individuals or external entities interacting with organizational systems are where they claim to be
- Support emergency response planning and incident verification by cross-referencing geolocation data
- Provide additional context for security investigations involving unauthorized access, social engineering, or online harassment

Without geolocation capabilities, operational teams may miss critical spatial clues that help verify incidents, strengthen security posture, and inform timely decisions. Research activities often involve fieldwork, environmental studies, global collaboration, or geospatial datasets. Effective geolocation and mapping practices protect research by helping verify the authenticity and origin of location-based data used in scientific analysis or publications, supporting researchers who analyze satellite imagery, remote sensing data, or environmental footage as part of their methods.

Geolocation also helps ensuring that sensitive field sites, lab locations, or protected datasets are not unintentionally exposed through images or metadata. It can also enhance the reliability of geospatial research outputs by validating the accuracy of location information

## Skill Development

- Explore: What types of metadata found in digital images are most useful for geolocation, and how can this data be extracted and verified?
- Explore: What type of Geolocation / OSINT challenges are available for people who wish to build identification skills?
- Reflect: How can landmark recognition and environmental analysis complement metadata to improve location accuracy?
- Reflect: What are the limitations of relying solely on EXIF data for geolocation in OSINT investigations?
- Reflect: How can open-source mapping tools and satellite imagery be integrated into the geolocation process during an investigation?
- Reflect: In what ways can geolocation findings support operational security assessments or threat actor tracking?
- Explore: How can the position of the sun and shadows in a photo help confirm a location or establish the time it was taken (chronolocation)? What tools support this?
- Reflect: Geolocating a *place* is different from locating a *person*. What privacy and safety harms can arise from geolocation, and when is it inappropriate to attempt to locate an individual from their images?

## Learning Resources

> **Ethics and safety note:** Geolocating a place for verification is very different from working out where an individual lives, works, or currently is. Using these techniques against a private person can enable stalking and harassment and may be unlawful; keep the focus on verifying content and authorized assessment, not tracking people. Remember too that your own and your organization's images can leak sensitive locations the same way — the techniques below reveal exposure as much as they exploit it.

### Reference and further reading

- [McMaster Library: OSINT and geolocation](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,OSINT,%20Geolocation&tab=Everything&search_scope=MyInst_and_CI&vid=01OCUL_MU:OMNI&lang=en&offset=0)
- [Wikipedia: Internet geolocation](https://en.wikipedia.org/wiki/Internet_geolocation) — note that this covers locating devices by IP address, a different technique from the image- and video-based geolocation that is the focus here.
  
### Metadata-based location clues

*Supports: Explore — useful metadata and extraction; Reflect — limits of EXIF*

- [ExifTool](https://exiftool.org/) — the standard tool for reading GPS and other location fields embedded in image and video files. (See also the Metadata Analysis page in this collection.)
- [Bellingcat: Metadata – MetaUseful & MetaCreepy](https://www.bellingcat.com/resources/how-tos/2017/02/22/metadata-metausefuland-metacreepy/) — how embedded location metadata helps investigators, and why it is unreliable on its own: most social platforms strip EXIF on upload, and it can be edited or absent. Grounds the "limits of EXIF" question.

### Visual geolocation techniques

*Supports: Reflect — landmark and environmental analysis; Reflect — integrating mapping and satellite imagery*

- [Bellingcat: A Beginner's Guide to Geolocating Videos](https://www.bellingcat.com/resources/how-tos/2017/06/30/beginners-guide-geolocating-videos/) — the classic walkthrough of placing imagery on a map using visible clues (signs, terrain, architecture) and cross-referencing with mapping tools.
- [Bellingcat: Geolocation Techniques – Mapping Landmarks](https://www.bellingcat.com/resources/how-tos/2014/07/09/geolocation-techniques-mapping-landmarks/) — how to triangulate a position from the relative placement of landmarks, directly supporting the landmark-recognition prompt.
- [GIJN: Searching the Earth / essential geolocation tools for verification](https://gijn.org/resource/guide-geolocation-tools-for-verification/) — a survey of mapping and imagery services and their regional strengths, useful because no single platform has the best coverage everywhere.

### Mapping tools and satellite imagery

*Supports: Reflect — integrating open-source mapping and satellite imagery*

- [Google Earth](https://earth.google.com/) — satellite and 3D imagery with a historical-imagery slider that lets you compare how a location looked on different dates, which supports both verification and chronolocation.
- [Mapillary](https://www.mapillary.com/) — crowdsourced street-level imagery (CC BY-SA) covering areas Google Street View does not, with free API access. Coverage is uneven because it depends on contributors.
- [Copernicus Browser (Sentinel Hub / EO Browser)](https://browser.dataspace.copernicus.eu/) — free access to recent Sentinel satellite imagery for overhead comparison and change-over-time analysis, useful for rural or fast-changing sites.
- [OpenStreetMap](https://www.openstreetmap.org/) — an open, editable map whose detail (building outlines, paths, labels) is often richer than commercial maps for matching ground features.

### Chronolocation: sun and shadows

*Supports: Explore — sun and shadow analysis*

- [SunCalc](https://www.suncalc.org/) — models the sun's position and the length and direction of shadows for any location, date, and time. Used both to estimate when a photo was taken (with a known location) and to help confirm a location (with a known time).
- [Bellingcat: Using the Sun and the Shadows for Geolocation](https://www.bellingcat.com/resources/2020/12/03/using-the-sun-and-the-shadows-for-geolocation/) — a worked example of using SunCalc for both chronolocation and geolocation.

### Building skills through challenges

*Supports: Explore — geolocation / OSINT challenges*

- [GeoGuessr](https://www.geoguessr.com/) — a game built on Street View that trains the habit of reading location clues quickly; widely used by OSINT practitioners to sharpen the skill.
- [Bellingcat / Sofia Santos: daily OSINT exercises (the Bellingcat Challenge)](https://challenge.bellingcat.com/) — regular geolocation and OSINT puzzles with worked solutions, for structured practice.
- [GIJN: The Daily Quiz That Teaches Journalists How to Geolocate Images (Quiztime)](https://gijn.org/stories/the-daily-quiz-that-teaches-journalists-how-to-geolocate-images/) — background on the @quiztime community, where players solve posted images and compare methods.

### Operational and intelligence context

*Supports: Reflect — supporting operational security and threat tracking*

- [Wikipedia: Geospatial intelligence (GEOINT)](https://en.wikipedia.org/wiki/Geospatial_intelligence) — background on how spatial analysis fits into formal intelligence work.
- [Neotas: Using Geolocation for OSINT Investigations](https://www.neotas.com/osint-sources-geolocation-osint/) — an applied overview oriented to investigations and risk assessment.
- [ShadowDragon: OSINT techniques](https://shadowdragon.io/resources/osint-techniques/) — where geolocation sits among the broader set of investigative techniques.


- [Authentic8: Geolocation 101 – image-based OSINT tips](https://authentic8.com/blog/geolocation-101-image-based-tips-and-inspiration-unlikely-places/)
