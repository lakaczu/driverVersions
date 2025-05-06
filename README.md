# driverVersions
Tools to help identify currently installed device drivers and Windows Updates. For personal use.

# Driver version script:

# Open PowerShell as an Administrator and run the following script
# Define the output file path
$outputFile = "C:\DriverVersions.csv"
# Get the list of installed drivers and their versions
$drivers = Get-WmiObject Win32_PnPSignedDriver | Select-Object DeviceName, DriverVersion, Manufacturer, DriverDate
# Export the driver information to a CSV file
$drivers | Export-Csv -Path $outputFile -NoTypeInformation
Write-Output "Driver information has been exported to $outputFile"


# Windows updates script:

# Open PowerShell as an Administrator and run the following script
# Define the output file path
$outputFile = "C:\InstalledUpdates.csv"
# Get the list of installed updates
$updates = Get-HotFix | Select-Object Description, HotFixID, InstalledOn
# Export the update information to a CSV file
$updates | Export-Csv -Path $outputFile -NoTypeInformation
Write-Output "Installed updates have been exported to $outputFile"
![image](https://github.com/user-attachments/assets/4e000bcb-c131-40dc-abd5-5f819e7bb4c5)
