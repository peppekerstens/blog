```powershell
Function Get-One{
    return $MyInvocation.MyCommand.Name
}
Function Get-OneThrow{
    $ErroractionPreference = 'Continue'
    Throw "$($MyInvocation.MyCommand.Name) Foutje!"
    return $null
}
Function Get-OneError{
    $ErroractionPreference = 'Continue'
    Write-Error -Message "$($MyInvocation.MyCommand.Name) Foutje!"
    return $null
}
Function Get-OneErrorBreak{
    $ErroractionPreference = 'Continue'
    Write-Error -Message "$($MyInvocation.MyCommand.Name) Foutje!"
    Break
}
```