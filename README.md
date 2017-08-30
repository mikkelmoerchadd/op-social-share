##ADD.ISS.ADFS

copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" copy "$(TargetDir).pdb" "$(ProjectDir)......\Website\bin"

xcopy "$(ProjectDir)\sitecore modules\shell\ADFS\s*.aspx" "$(ProjectDir)......\Website\sitecore modules\shell\ADFS" /Y /E xcopy "$(ProjectDir)\sitecore modules\shell\ADFS\l*.aspx" "$(ProjectDir)......\Website\sitecore modules\shell\ADFS" /Y /E

copy "$(ProjectDir)R*.aspx" "$(ProjectDir)......\Website\layouts"

rem copy "$(ProjectDir)c*.aspx" "$(ProjectDir)......\Website\layouts\scripts" rem copy "$(ProjectDir)e*.aspx" "$(ProjectDir)......\Website\layouts\scripts"

##ADD.ISS.Base

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin $(TargetName).* /NP /NJH /NJS

copy "$(ProjectDir)......\Libs\Sitecore.Forms.Core.dll" "$(ProjectDir)......\Website\bin" copy "$(ProjectDir)......\Libs\Sitecore.Forms.Custom.dll" "$(ProjectDir)......\Website\bin"

xcopy "$(ProjectDir)\Developerfolder*.aspx" "$(ProjectDir)......\Website\Developerfolder" /Y /E xcopy "$(ProjectDir)\Developerfolder*.master" "$(ProjectDir)......\Website\Developerfolder" /Y /E xcopy "$(ProjectDir)\Developerfolder*.ascx" "$(ProjectDir)......\Website\Developerfolder" /Y /E xcopy "$(ProjectDir)\Developerfolder\images*" "$(ProjectDir)......\Website\Developerfolder\images" /Y /E

xcopy "$(ProjectDir)\Configuration\Sc.Customizations\CreateNewUser.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\Security\CreateNewUser" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.Countries

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\Internet\Components*.ascx" "$(ProjectDir)......\Website\Layouts\Internet\Components" /Y /E xcopy "$(ProjectDir)\Layouts\Internet\ISSWorld*.ascx" "$(ProjectDir)......\Website\Layouts\Internet\ISSWorld" /Y /E xcopy "$(ProjectDir)\Layouts\Internet\Main*.as?x" "$(ProjectDir)......\Website\Layouts\Internet\Base" /Y /E

xcopy "$(ProjectDir)\Layouts\Intranet\Components*.ascx" "$(ProjectDir)......\Website\Layouts\Intranet\Components" /Y /E xcopy "$(ProjectDir)\Layouts\Intranet\ISSIntranet*.ascx" "$(ProjectDir)......\Website\Layouts\Intranet\ISSIntranet" /Y /E xcopy "$(ProjectDir)\Layouts\Intranet\Main*.as?x" "$(ProjectDir)......\Website\Layouts\Intranet\Base" /Y /E

xcopy "$(ProjectDir)\Layouts\ClientSite\Components*.ascx" "$(ProjectDir)......\Website\Layouts\ClientSite\Components" /Y /E xcopy "$(ProjectDir)\Layouts\ClientSite\ISSClient*.ascx" "$(ProjectDir)......\Website\Layouts\ClientSite\ISSClient" /Y /E xcopy "$(ProjectDir)\Layouts\ClientSite\Main*.aspx" "$(ProjectDir)......\Website\Layouts\ClientSite\Base" /Y /E

xcopy "$(ProjectDir)\Layouts\Basic\Components*.ascx" "$(ProjectDir)......\Website\Layouts\Basic\Components" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\Components*.aspx" "$(ProjectDir)......\Website\Layouts\Basic\Components" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\Components\Internal Vacancies*.ascx" "$(ProjectDir)......\Website\Layouts\Basic\Components\Internal Vacancies" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\Components\Internal Vacancies\Ajax*.aspx" "$(ProjectDir)......\Website\Layouts\Basic\Components\Internal Vacancies\Ajax" /Y /E

xcopy "$(ProjectDir)\Layouts\Basic\ISSBasic*.ascx" "$(ProjectDir)......\Website\Layouts\Basic\ISSBasic" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\OEService*.asmx" "$(ProjectDir)......\Website\Layouts\Basic\OEService" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\ISSBasic*.aspx" "$(ProjectDir)......\Website\Layouts\Basic\ISSBasic" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\Main*.aspx" "$(ProjectDir)......\Website\Layouts\Basic\Base" /Y /E xcopy "$(ProjectDir)\Layouts\Basic\Backend Content*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\SiteControlPanelForms" /Y /E xcopy "$(ProjectDir)\Layouts\Shared*.ascx" "$(ProjectDir)......\Website\Layouts\Shared" /Y /E xcopy "$(ProjectDir)\App_Config\Include*.config" "$(ProjectDir)......\Website\App_Config\Include" /Y /E

xcopy "$(ProjectDir)\Services\CateringService.svc" "$(ProjectDir)......\Website\Services\CateringService.svc" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.DynamicForms

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin $(TargetName).* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\DynamicForms*.ascx" "$(SolutionDir)....\Website\Layouts\Internet\Components\DynamicForms" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.Environment

xcopy "$(ProjectDir)DEV-CM01\App_Config*" "$(ProjectDir)......\Website\App_Config" /Y /E xcopy "$(ProjectDir)DEV-CM01*.config" "$(ProjectDir)......\Website" /Y /E xcopy "$(ProjectDir)DEV-CM01\sitecore modules*" "$(ProjectDir)......\Website\sitecore modules" /Y /E

del "$(ProjectDir)......\Website\bin\Sitecore.SignalR.dll /q del "$(ProjectDir)......\Website\bin\Sitecore.SignalR.pdb /q

del "$(ProjectDir)......\Website\App_Config\Include\Sitecore.SignalR.config" /q

xcopy "$(ProjectDir)DEV-CM01\App_Config\Include\ScalabilitySettings.disabled" "$(ProjectDir)......\Website\App_Config\Include\ScalabilitySettings.config" /Y /E

##ADD.ISS.Great

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\Great\Components*.ascx" "$(ProjectDir)......\Website\Layouts\Great\Components" /Y /E xcopy "$(ProjectDir)\Layouts\Great\ISSGreat*.ascx" "$(ProjectDir)......\Website\Layouts\Great\ISSGreat" /Y /E xcopy "$(ProjectDir)\Layouts\Great\Main*.aspx" "$(ProjectDir)......\Website\Layouts\Great\Base" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.InsideNews

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\InsideNews\Components*.ascx" "$(ProjectDir)......\Website\Layouts\InsideNews\Components" /Y /E

xcopy "$(ProjectDir)\Layouts\InsideNews\ISSInsideNews*.ascx" "$(ProjectDir)......\Website\Layouts\InsideNews\ISSInsideNews" /Y /E

xcopy "$(ProjectDir)\Layouts\InsideNews\Main*.aspx" "$(ProjectDir)......\Website\Layouts\InsideNews\Base" /Y /E

copy "$(ProjectDir)\News Archive\WebEdit*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\WebEdit"

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.LEB

copy "$(ProjectDir).as?x" "$(ProjectDir)......\Website\Layouts\LebForm" xcopy "$(TargetDir).*" "$(ProjectDir)......\Website\bin" /Y /E

##ADD.ISS.LMS

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\Intranet\Components*.ascx" "$(ProjectDir)......\Website\Layouts\Intranet\Components" /Y /E

xcopy "$(ProjectDir)\Layouts\Scripts*.aspx" "$(ProjectDir)......\Website\Layouts\Scripts" /Y /E

xcopy "$(ProjectDir)\Layouts\Intranet\ISSIntranet*.ascx" "$(ProjectDir)......\Website\Layouts\Intranet\ISSIntranet" /Y /E

xcopy "$(ProjectDir)\sitecore modules\Addition\AdditionFramework\Forms\WebEdit*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\WebEdit" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ADD.ISS.SignalR

copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" copy "$(TargetDir).pdb" "$(ProjectDir)......\Website\bin"

##Foundation.Custom

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin $(TargetName).* /NP /NJH /NJS

rem robocopy $(ProjectDir)Website\layouts\components $(ProjectDir)......\Website\layouts\components *.as?x /S /NJH /NJS /NP /PURGE /XD .svn

robocopy $(ProjectDir)Website\App_Config\Include $(ProjectDir)......\Website\App_Config\Include *.config /S /NP /NJH /NJS

rem robocopy $(ProjectDir)Website\xsl\Components $(ProjectDir)......\Website\xsl\components *.xslt /S /NJH /NJS /NP /PURGE /XD .svn

xcopy "$(ProjectDir)\Scripts*.aspx" "$(ProjectDir)......\Website\Layouts\Scripts" /Y /E

rem robocopy $(ProjectDir)website\sitecore $(ProjectDir)......\Website\sitecore *.as?x /S /NJH /NJS /NP /XD .svn echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##Foundation.Deploy

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin $(TargetName).* /NP /NJH /NJS

rem robocopy $(ProjectDir)Website\layouts\components $(ProjectDir)......\Website\layouts\components *.as?x /S /NJH /NJS /NP /PURGE /XD .svn

robocopy $(ProjectDir)App_Config\Include $(ProjectDir)......\Website\App_Config\Include *.config /S /NP /NJH /NJS

rem robocopy $(ProjectDir)Website\xsl\Components $(ProjectDir)......\Website\xsl\components *.xslt /S /NJH /NJS /NP /PURGE /XD .svn

xcopy "$(ProjectDir)\Scripts*.aspx" "$(ProjectDir)......\Website\Layouts\Scripts" /Y /E

rem robocopy $(ProjectDir)website\sitecore $(ProjectDir)......\Website\sitecore *.as?x /S /NJH /NJS /NP /XD .svn echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##Foundation.Modules

rem copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" echo Copying $(ProjectName) elements to Sitecore website ....\Website copy "$(TargetDir)$(TargetName)." "$(ProjectDir)......\Website\bin"

robocopy $(TargetDir) $(ProjectDir)......\Website\bin $(TargetName).* /NP /NJH /NJS

copy "$(TargetDir)EntityFramework.*" "$(ProjectDir)......\Website\bin"

copy "$(ProjectDir)SiteControlPanelForms*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\SiteControlPanelForms" xcopy "$(ProjectDir)sitecore modules*" "$(ProjectDir)......\Website\sitecore modules" /Y /E copy $(ProjectDir)Foundation.Modules.config $(ProjectDir)......\Website\App_Config\Include
echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##Foundation.SiteManagement

echo Copying $(ProjectName) elements to Sitecore website ....\Website

copy "$(TargetDir)$(TargetName).pdb" "$(ProjectDir)......\Website\bin" copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" xcopy "$(ProjectDir)SiteManager\sitecore\shell\client\addition*." "$(ProjectDir)......\Website\sitecore\shell\client\addition" /Y /E xcopy "$(ProjectDir)Forms\SiteControlPanelForms*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\SiteControlPanelForms" /Y /E xcopy "$(ProjectDir)Forms\SiteProvisioningForms*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\SiteProvisioningForms" /Y /E xcopy "$(ProjectDir)Forms*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms" /Y /E xcopy "$(ProjectDir)Forms\WebEdit*.aspx" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\Forms\WebEdit" /Y /E

xcopy "$(ProjectDir)Editors\EditUserCustom.xaml.xml" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\UserManager" /Y /E xcopy "$(ProjectDir)Members\EditMemberCustom.xaml.xml" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework\UserManager" /Y /E xcopy "$(ProjectDir)Editors\SecurityEditorWorkFlow.xml" "$(ProjectDir)......\Website\sitecore\shell\Applications\Addition\AdditionFramework\UserManager\SecurityEditorWorkFlow" /Y /E xcopy "$(ProjectDir)Members\UserManagerMembers.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\Addition\AdditionFramework\UserManager\UserManagerMembers" /Y /E xcopy "$(ProjectDir)Editors\UserManagerEditors.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\Addition\AdditionFramework\UserManager\UserManagerEditors" /Y /E xcopy "$(ProjectDir)Members\UserManagerMembersDisabled.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\Addition\AdditionFramework\UserManager\UserManagerMembers" /Y /E xcopy "$(ProjectDir)Editors\SecurityEditorWorkFlow.xml" "$(ProjectDir)......\Website\sitecore\shell\Applications\AdditionUserManager\SecurityEditorWorkFlow" /Y /E xcopy "$(ProjectDir)Editors\UserManagerEditors.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\AdditionUserManager\UserManagerEditors" /Y /E xcopy "$(ProjectDir)Members\UserManagerMembers.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\AdditionUserManager\UserManagerMembers" /Y /E xcopy "$(ProjectDir)Members\UserManagerMembersDisabled.aspx" "$(ProjectDir)......\Website\sitecore\shell\Applications\AdditionUserManager\UserManagerMembers" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##Foundation.UI

echo Copying $(ProjectName) elements to Sitecore website ....\Website

copy "$(TargetDir)." "$(ProjectDir)......\Website\bin" copy "$(TargetDir)*.dll" "$(ProjectDir)......\Website\bin"

copy $(ProjectDir)Website\App_Config\Include*.* $(ProjectDir)........\Website\App_Config\Include\

xcopy "$(ProjectDir)\Website*.as*x" "$(ProjectDir)......\Website" /Y /E

xcopy "$(ProjectDir)\Scripts*.aspx" "$(ProjectDir)......\Website\Layouts\Scripts" /Y /E copy "$(ProjectDir)*.xml" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework"

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ISS.APP.SupplierCM.WebApplication

robocopy $(TargetDir) $(ProjectDir)..........\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\Layouts\SupplierCM*.ascx" "$(ProjectDir)..........\Website\Layouts\Basic\Components\SupplierCM" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##ISS.Direct

copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" copy "$(TargetDir).pdb" "$(ProjectDir)......\Website\bin"

copy "$(ProjectDir)Global.asax" "$(ProjectDir)......\Website" xcopy "$(ProjectDir)App_Config*.*" "$(ProjectDir)......\Website\App_Config" /Y /E

xcopy "$(ProjectDir)Areas*.config" "$(ProjectDir)......\Website\Areas" /Y /E xcopy "$(ProjectDir)Areas*.cshtml" "$(ProjectDir)......\Website\Areas" /Y /E

xcopy "$(ProjectDir)CSS*." "$(ProjectDir)......\Website\CSS" /Y /E xcopy "$(ProjectDir)Fonts*." "$(ProjectDir)......\Website\Fonts" /Y /E xcopy "$(ProjectDir)Images*." "$(ProjectDir)......\Website\Images" /Y /E xcopy "$(ProjectDir)ISSDirect*." "$(ProjectDir)......\Website\ISSDirect" /Y /E xcopy "$(ProjectDir)scripts\ISSDirect*.*" "$(ProjectDir)......\Website\scripts\ISSDirect" /Y /E xcopy "$(ProjectDir)sitecore*.aspx" "$(ProjectDir)......\Website\sitecore" /Y /E

##ISS.Direct.Entities

copy "$(TargetDir).dll" "$(ProjectDir)......\Website\bin" copy "$(TargetDir).pdb" "$(ProjectDir)......\Website\bin"

##Sitecore.Foundation.SitecoreExtensions

echo Copying $(ProjectName) elements to Sitecore website ....\Website

copy "$(TargetDir)." "$(ProjectDir)......\Website\bin" copy "$(TargetDir)*.dll" "$(ProjectDir)......\Website\bin"

xcopy "$(ProjectDir)App_Config\Include*.*" "$(ProjectDir)......\Website\App_Config\Include" /Y /E

xcopy "$(ProjectDir)\Website*.as*x" "$(ProjectDir)......\Website" /Y /E

xcopy "$(ProjectDir)\Scripts*.aspx" "$(ProjectDir)......\Website\Layouts\Scripts" /Y /E copy "$(ProjectDir)*.xml" "$(ProjectDir)......\Website\sitecore modules\Addition\AdditionFramework"

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0

##Sitecore.Modules.Calendar

echo Copying $(ProjectName) elements to Sitecore website ......\Website

robocopy $(TargetDir) $(ProjectDir)......\Website\bin * .* /NP /NJH /NJS

xcopy "$(ProjectDir)\sitecore\shell*" "$(ProjectDir)......\Website\sitecore\shell" /Y /E

xcopy "$(ProjectDir)\sitecore modules\shell\sitecore.calendar*" "$(ProjectDir)......\Website\sitecore modules\shell\sitecore.calendar" /Y /E

xcopy "$(ProjectDir)\App_Config\Include*.config" "$(ProjectDir)......\Website\App_Config\Include" /Y /E

echo Done

if errorlevel 4 goto BuildEventFailed if errorlevel 0 goto end :BuildEventFailed echo FILECOPY for $(ProjectName) FAILED exit 1 :end echo FILECOPY for $(ProjectName) COMPLETED OK exit 0
