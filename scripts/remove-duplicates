#!/usr/bin/env pwsh

# Get the content of the "ultimate_trackers.txt" file
$content = Get-Content ./ultimate_trackers.txt

# Group the content by identical lines, filter for groups with more than one item (duplicates),
# and extract the duplicate lines
@(($content | Group-Object).Where({ $_.Count -gt 1 }).Name).ForEach({ Write-Host "Duplicate found: $_" })

# Create a new array with unique lines from the original content,
# separating each line with an empty line for better readability
$sortedContent = @($content | Select-Object -Unique).ForEach({ "$_`n" })

# Overwrite the original file with the sorted, unique content
$sortedContent | Select-Object -Skip 1 | Out-String | Set-Content ./ultimate_trackers.txt -Force -NoNewline
