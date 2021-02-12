# EQN detections between 2017-12-15 and 2020-01-31

## Introduction

The 'Earthquake Network’ (EQN) is an app which detects earthquakes by creating an ad-hoc network of smartphones' accelerometer sensors and provides early warnings for earthquakes via the same smartphone app. Detections are not due to individual smartphone measurements but due to near-simultaneous trigger signals from clusters of smartphones running the app.

This analysis was conducted on detections by the EQN system between 2017-12-15 and 2020-01-31 in order to test it's performance and whether EQN detections are fast enough to provide early warnings of earthquakes to its users.

This dataset and analysis is a supplement to the article Bossu et al. "Shaking in 5 seconds!" A Voluntary Smartphone-based Earthquake Early Warning System (2021) 

## D1  - eqn_article_D1_usa_chl_ita.csv

This dataset contains the 550 detections made by EQN between 2017-12-15 and 2020-01-31 in Chile, USA and Italy. Each detection was associated with an earthquake from the parameter catalogue of each countries foremost seismic insitute (CSN for Chile, USGS for USA and INGV for Italy) wherever possible (initially automatically and also checked manually).

The csv file uses ',' separators and its first row contains the field headers. A description of each field is found in the table below.

## D2 - eqn_article_D2_mag_gt_4.5.csv

This dataset contains 134 detections from around the world that could be associated to earthquakes (in the USGS earthquake parameter catalogue) with magnitude ≥ M5 or magnitude ≥ M4.5 in Italy and the USA. There are 68 detections that are common to the D1 dataset.

The csv file uses ',' separators and its first row contains the field headers. A description of each field is found in the table below. Note that this dataset doesn't have the final 16 fields described in that table


## dataset description

| Field | Description |
|--------|----------------|
|peakid | Each EQN detection has a random 7 digit numeric id associated.
|det_lat | Latitude where EQN detection occurred (degrees).
|det_lon | Longitude where EQN detection occurred (degrees).
|country | Country iso3166 code, one of {‘chl’,’usa’,’ita’}.
|detectiontime | Date and time of EQN detection (Iso8166 format) (UTC time zone).
|detectiontime_local | Localised date and time of EQN detection.
|pytz | Time zone of EQN detection.
|nighttime | Did EQN detection occur between 23h and 7h local time? (Boolean)
|signals | The number of signals that caused the EQN detection to trigger.
|actives | The number of active EQN apps within 30 km of the detection location.
|felt_reports_green | Number of felt reports collected indicating 'green' within 3 min from detection and within a radius of 300 km.
|felt_reports_yellow | Number of felt reports collected indicating 'yellow' within 3 min from detection and within a radius of 300 km.
|felt_reports_red | Number of felt reports collected indicating 'red' within 3 min from detection and within a radius of 300 km.
|notification_time | When the notification based on felt reports was sent to the Firebase notification service.
|notification_delay_from_detection | Delay between detection and the notification.
|Intensity_strong | If 1, a second alert for strong earthquakes was sent. The time of this second alert is the same of notification_time since it is based on the felt reports.
|cat | Seismic catalogue used for earthquake parameters.
|num_eq_matches | Number of potentially associated earthquakes in catalogue.
|origintime | Date and time of associated earthquake in catalogue (UTC).
|magtype | Type of magnitude for associated earthquake.
|magnitude | Magnitude of associated earthquake in catalogue.
|eq_lat | Latitude of associated earthquake in catalogue (deg).
|eq_lon | Longitude of associated earthquake in catalogue (deg).
|depth | Depth of associated earthquake in catalogue (km).
|separation | Separation of EQN detection from epicentre of associated parameters.
|detectiondelay | Delay between origintime and EQN detection (s).
|P_at_surface_delay | Delay for P wave to reach the Earth’s surface (s).
|offshore | Was earthquake offshore? (Boolean).
|dist_shore | Distance from epicentre to closest point on the shore (km).
|closest_land_lat | Latitude of point of coast closest to the epicentre (deg).
|closest_land_lon | Longitude of point of coast closest to the epicentre (deg).
|P_at_coast_delay | Delay for P wave to reach the closest point on the coastline (and at the surface) (s).
|P_on_land_surface_delay | Delay for the P wave to read the surface (or the coast if applicable) (s).
|detectiondelay_wrt_P | Delay between the P wave arriving at the EQN detection location and the detection time (s).
|detectiondelay_wrt_S | Delay between the S wave arriving at the EQN detection location and the detection time (s).
|causal_phase | Whether the EQN detection was estimated to have been caused by the P wave or the S wave.
|intensity_at_0ld | The predicted intensity of the earthquake for the location of the S wave at the moment of the EQN detection.
|intensity_at_5ld | The predicted intensity of the earthquake at locations with a lead time of 5 s with respect to the S wave at the moment of the EQN detection.
|intensity_at_10ld | The predicted intensity of the earthquake at locations with a lead time of 10 s with respect to the S wave at the moment of the EQN detection.
|intensity_at_15ld | The predicted intensity of the earthquake at locations with a lead time of 15 s with respect to the S wave at the moment of the EQN detection.
|sm_net | The seismic network if strong motion accelerometer data was found nearby.
|sm_sta | The station name if strong motion accelerometer data was found nearby.
|sm_loc | The separation between the strong motion station and the EQN station (km).
|sm_unit | One of {‘acc’,’vel’,’disp’} where acc is acceleration (m/s/s), vel is velocity (m/s) and disp is displacement (m).
|sm_sta_lat | Latitude of strong motion station (deg).
|sm_sta_lon | Longitude of strong motion station (deg).
|sm_sta_elv | Elevation of strong motion station (m).
|sm_sep_eqn_sta | Separation between EQN detection and strong motion station (km).
|sm_strongest_motion | Strongest value recorded by station.
|sm_strong_motion_time | Time of strongest motion (this already accounts for sm_dt_correction).
|sm_strongest_motion_eqn_delay | Delay between strong motion and EQN detection (this already accounts for sm_dt_correction).
|sm_dt_correction | Time correction (s) due to difference in distances of station and EQN detection from the epicentre. A velocity of 8 km/s is used to convert between distance and time.


