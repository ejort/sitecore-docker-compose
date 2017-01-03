FROM microsoft/aspnet

RUN mkdir C:\site

RUN set-itemproperty -path 'HKLM:\SYSTEM\CurrentControlSet\Services\Dnscache\Parameters' -Name ServerPriorityTimeLimit -Value 0 -Type DWord

RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "Sitecore" -PhysicalPath C:\site -BindingInformation "*:8000:"

EXPOSE 8000