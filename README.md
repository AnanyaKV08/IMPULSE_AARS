# IMPULSE_AARS
Agriculture crop disease prediction
Crop disease warning and mitigation

make sure you upload the 4 images from the drive link given: https://drive.google.com/drive/folders/1cTF-87HCAHJah18LyCWzU33l6hmm35Gl?usp=sharing

Our main aim is to help farmer bodies identify crop that are either susceptible to or have already got certain diseases affecting their variety.

We have developed a website www.google.com which contain a wide range of information regarding some of the major crops in the country, conditions for their healthy growth,diseases associated with them, prevention and mitigation methods etc..

Once a farmer or a member from any Krishi Bhavan enrolls with us via the website by giving us the location details of area he would like us to survey on, his contact info etc.. we will start the process of our analysis.

1st step would be to find out the major crop in the particular location(if more than one, divide area of interest into smaller parts), this will be our AOI(Area of interest).

next we will aquire satellite images in geo tif format from websites like USDS in 4 bands(R G B IR). Additional images we would aquire from them are the temperature, humidity and rainfall heat maps of the same area of interest or research on weather conditions from weather stations in the area.

These will be our inputs to the below given code.

Here firstly we have worked on creating the NDVI(Normalized Difference Vegetation Index) image of the AOI. This is done by 1st getting the red and IR band images of the same and finding out the NDVI pixel data value from the formula: NDVI=NIR-RED/NIR+RED The NVDI tells is basic terms gives us info as to what values of refluctance is shown by each part. Greater value indicating higher refluctance. By usual analysis we can say that low NDVI values indicate sandy or rocky terrains and high values indicate dense forest. Hence crops like sugarcane, rice etc.. come under mid range of NDVI values. We can gone through papers and articles on typical NDVI values which showed gave us a range of NDVI values that could possibly indicate lesser healthy crops.

We have considered a test case here where a person had enrolled with us from Gularia UP and the area of interest is dominated by sugarcane crops. The geo tig image of the area aquired was a recent one dated 23rd of April which suggests is the growing season for sugarcane. We found the NDVI imagery of the same and colour coded for better understanding (breifly red indicating lower refluctance, yellow moderate and green high). Along with this we have also plotted a histogram that shows the number of pixels(amount of area) vs NDVI values which shows maximum of it lies in the higher range on NDVI(healthy crop) and lower most range(hilly terrain and rocks). From here we calculated the index of pixel data values that indicated an Ndvi value corresponding to neither extremes not operfectly healthy crops. Hence we get an apoximate region where diseases might have occured or are likely to occur.

Upon due research we understood that crop diseases occur due to prolonged weather Conditions(temperature,rainfall,humidity), hence these parameters were key to confirm presence of crop diseases as well as identification of the disease. There are 11 major crop diseases associated with sugarcane(details of which are on the website) among which 3 are mostly found in our considered AOI. upon doing our research we found out the combination of the 3 parameters(temperature,rainfall,humidity) that cause these diseases, eg: Redrot is caused due to higher values of all the 3 parameters whereas Brown rust disease is caused in moderate temperatures, low rainfall and high humidity. hence we mapped the pixel values we got from the NVDI imagery and checked corresponding values in the temperature, rainfall and humidity heat maps of the same area.(we plotted te histograms of these maps as well inorder to obtain accurate ranges that come under low moderate and high).

upon doing this we got rid of some area that didnt favor any of these diseases therefore mightve have a lower NDVI values due to other reasons like late sowing, houses,lack of nutrition etc.. The rest of the area fell into the above categorised diseases. From this analysis we got the percentge crops affected or in threat of the particular diseases, location of areas in which the disease is found as well as a link redirecting to our website(page with info on the diseases detected, and how to prevent them and cure the crops) which is sent via email to the concerned person or authority.
