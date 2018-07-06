# Days-from-birth-calculator


ian = 31 
feb = 28 + ian 
mar = 31 + feb 
apr = 30 + mar  
mai = 31 + apr  
iun = 30 + mai  
iul = 31 + iun  
aug = 31 + iul   
sep = 30 + aug   
octo = 31 + sep  
noi = 30 + octo  
dec = 31 + noi   
month = [0,0,ian,feb,mar,apr,mai,iun,iul,aug,sep,octo,noi,dec]
def daysBetweenDates(year1, month1, day1, year2, month2, day2):
  year_a = year1 * 365 + month[month1] + day1 
  year_b = year2 * 365 + month[month2] + day2 
  leap_days1 = 1
  leap_days2 = 1
  for i in range(0,year1 +1):
    if ((i % 4 == 0 or i % 400 == 0 )and i % 100 != 0) :
      leap_days1 += 1
  
  for i in range(0,year2 + 1 ):
    if ((i % 4 == 0 or i % 400 == 0 )and i % 100 != 0)  :
      leap_days2 += 1    
  if (year1 % 4 == 0 and year1 % 100 != 0) and month1 <3:
    leap_days1 -=1
  if (year2 % 4 == 0 and year2 % 100 != 0) and month2 <3:
    leap_days2 -=1    
    
  

  return int(year_b - year_a) + (leap_days2 - leap_days1)
  
