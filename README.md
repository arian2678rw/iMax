# iMax
#include "Includes\AutomatingWindowsExplorer.au3" #include &lt;Array.au3>  Opt( "MustDeclareVars", 1 )  Example()  Func Example()   ; Windows Explorer on XP, Vista, 7, 8   Local $hExplorer = WinGetHandle( "[REGEXPCLASS:^(Cabinet|Explore)WClass$]" )   If Not $hExplorer Then     MsgBox( 0, "Automating Windows Explorer", "Could not find Windows Explorer. Terminating." )     Return   EndIf    ; Get an IShellBrowser interface   GetIShellBrowser( $hExplorer )   If Not IsObj( $oIShellBrowser ) Then     MsgBox( 0, "Automating Windows Explorer", "Could not get an IShellBrowser interface. Terminating." )     Return   EndIf    ; Get other interfaces   GetShellInterfaces()    ; Get all folders   ;GetFolders( $fSelected = False, $fFullPath = False, $fPidl = False, $iMax = 0 )   Local $aFolders = GetFolders()   _ArrayDisplay( $aFolders, "All folders" )    ; Get selected folders   ;GetFolders( $fSelected = False, $fFullPath = False, $fPidl = False, $iMax = 0 )   $aFolders = GetFolders( True )   _ArrayDisplay( $aFolders, "Selected folders" ) EndFunc
