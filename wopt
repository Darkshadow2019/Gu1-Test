# Add the required .NET assemblies for creating a GUI
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

# Set the script's behavior
Set-StrictMode -Version Latest
$ErrorActionPreference = "Stop"

# Create the main form for the GUI
$mainForm = New-Object System.Windows.Forms.Form
$mainForm.Text = "Windows Optimization Utility"
$mainForm.Size = New-Object System.Drawing.Size(400, 350)
$mainForm.StartPosition = "CenterScreen"
$mainForm.FormBorderStyle = "FixedSingle"
$mainForm.MaximizeBox = $false

# Create a label for the title
$titleLabel = New-Object System.Windows.Forms.Label
$titleLabel.Text = "Windows Optimization Utility"
$titleLabel.Font = New-Object System.Drawing.Font("Segoe UI", 16, [System.Drawing.FontStyle]::Bold)
$titleLabel.Location = New-Object System.Drawing.Point(20, 20)
$titleLabel.AutoSize = $true
$mainForm.Controls.Add($titleLabel)

# Create a status label to show progress or messages
$statusLabel = New-Object System.Windows.Forms.Label
$statusLabel.Text = "Status: Ready to optimize."
$statusLabel.Location = New-Object System.Drawing.Point(20, 290)
$statusLabel.AutoSize = $true
$statusLabel.ForeColor = "DarkGreen"
$mainForm.Controls.Add($statusLabel)

# --- Define the functions for each task (These are placeholders) ---

# Function for optimizing Windows
Function Optimize-Windows {
    # Update status label to show progress
    $statusLabel.Text = "Status: Optimizing Windows, please wait..."
    # The [System.Windows.Forms.Application]::DoEvents() line forces the GUI to update
    [System.Windows.Forms.Application]::DoEvents()

    # Place your optimization commands here
    # Example: Disabling unnecessary services, cleaning up temp files
    # Get-Service -Name "SysMain" | Stop-Service -Force -ErrorAction SilentlyContinue
    # Get-ChildItem -Path $env:TEMP -Recurse | Remove-Item -ErrorAction SilentlyContinue

    Start-Sleep -Seconds 2 # Simulate the process
    $statusLabel.Text = "Status: Windows optimization complete."
}

# Function for privacy settings
Function Apply-PrivacySettings {
    $statusLabel.Text = "Status: Applying privacy settings..."
    [System.Windows.Forms.Application]::DoEvents()

    # Place your privacy-related commands here
    # Example: Disabling telemetry, Cortana, etc.
    # Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DataCollection" -Name "AllowTelemetry" -Value 0

    Start-Sleep -Seconds 2 # Simulate the process
    $statusLabel.Text = "Status: Privacy settings applied."
}

# Function for installing applications
Function Install-CommonApps {
    $statusLabel.Text = "Status: Installing common applications..."
    [System.Windows.Forms.Application]::DoEvents()

    # Place your app installation commands here
    # Example using Winget:
    # winget install --id "Mozilla.Firefox" -e
    # winget install --id "VLC.VLC" -e

    Start-Sleep -Seconds 2 # Simulate the process
    $statusLabel.Text = "Status: Common applications installed."
}

# --- Create the buttons and link them to the functions ---

# Optimize Button
$optimizeBtn = New-Object System.Windows.Forms.Button
$optimizeBtn.Text = "Optimize Windows"
$optimizeBtn.Location = New-Object System.Drawing.Point(20, 70)
$optimizeBtn.Size = New-Object System.Drawing.Size(150, 40)
$optimizeBtn.Add_Click({ Optimize-Windows })
$mainForm.Controls.Add($optimizeBtn)

# Privacy Button
$privacyBtn = New-Object System.Windows.Forms.Button
$privacyBtn.Text = "Apply Privacy Settings"
$privacyBtn.Location = New-Object System.Drawing.Point(20, 120)
$privacyBtn.Size = New-Object System.Drawing.Size(150, 40)
$privacyBtn.Add_Click({ Apply-PrivacySettings })
$mainForm.Controls.Add($privacyBtn)

# Install Apps Button
$installAppsBtn = New-Object System.Windows.Forms.Button
$installAppsBtn.Text = "Install Common Apps"
$installAppsBtn.Location = New-Object System.Drawing.Point(20, 170)
$installAppsBtn.Size = New-Object System.Drawing.Size(150, 40)
$installAppsBtn.Add_Click({ Install-CommonApps })
$mainForm.Controls.Add($installAppsBtn)

# Show the GUI form
$mainForm.ShowDialog() | Out-Null
