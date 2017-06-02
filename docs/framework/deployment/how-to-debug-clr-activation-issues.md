---
title: "C&#243;mo: Depurar problemas de activaci&#243;n de CLR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "activación de direcciones CLR, depurar problemas"
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Depurar problemas de activaci&#243;n de CLR
Si tiene problemas cuando intenta que su aplicación se ejecute con la versión correcta del runtime de lenguaje común \(CLR, por sus siglas en inglés\), puede ver y depurar los registros de activación del CLR.  Estos registros pueden ser muy útiles para determinar la causa principal de un problema de activación, cuando la aplicación o bien carga una versión diferente de CLR a la que se esperaba o no la carga.  [Errores de inicialización de .NET Framework: Administrar la experiencia del usuario](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md) describe este proceso cuando no hay disponible ningún CLR para una aplicación.  
  
 El registro de activación de CLR puede activarse en todo el sistema mediante una clave de registro HKEY\_LOCAL\_MACHINE o una variable de entorno del sistema.  El registro se generará hasta que la entrada del Registro o la variable de entorno se elimine.  Alternativamente, se puede utilizar una variable de entorno de usuario o de proceso local para habilitar el registro con un alcance y duración diferentes.  
  
 Los registros de activación de CLR no deben confundirse con los registros de enlace de ensamblados [](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md "Fuslogvw.exe (Assembly Binding Log Viewer)"), que son completamente diferentes.  
  
## Cómo habilitar el registro de activación de CLR  
  
#### Utilización del registro  
  
1.  En el Editor del Registro, navegue a HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework \(en un equipo de 32 bits\) o a HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework \(en un equipo de 64 bits\).  
  
2.  Agregue un valor de cadena denominado `CLRLoadLogDir`, y establézcalo en la ruta de acceso completa de un directorio existente, donde desee almacenar los registros de activación de CLR.  
  
 El registro de activación sigue habilitado hasta que se quite el valor de cadena.  
  
#### Utilización de una variable de entorno  
  
-   Establezca la variable de entorno `COMPLUS_CLRLoadLogDir` a una cadena que representa la ruta de acceso completa de un directorio existente en el que desee almacenar los registros de activación de CLR.  
  
     Cómo se establezca la variable de entorno determinará su alcance:  
  
    -   Si se establece en el nivel del sistema, el registro de activación estará habilitado para todas las aplicaciones de .NET Framework en ese equipo hasta que se quite la variable de entorno.  
  
    -   Si se establece en el nivel de usuario, el registro de activación se habilitará únicamente para la cuenta de usuario.  El registro continúa hasta que se quite la variable de entorno.  
  
    -   Si se establece en el proceso antes de cargar el CLR, el registro de activación estará habilitado hasta que el proceso finalice.  
  
    -   Si se establece en un símbolo del sistema antes de ejecutar una aplicación, el registro de activación se habilita para cualquier aplicación que se ejecute desde dicho símbolo del sistema  
  
     Por ejemplo, para almacenar los registros de activación en el directorio c:\\clrloadlogs con alcance a nivel de procesos, abra una ventana de símbolo del sistema y escriba lo siguiente antes de ejecutar la aplicación:  
  
    ```  
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs  
    ```  
  
## Ejemplo  
 Los registros de activación de CLR ofrecen una gran cantidad de datos sobre la activación de CLR y el uso de las API que alojan CLR.  La mayoría de estos datos los utiliza Microsoft internamente, pero algunos de los datos también pueden ser útiles para los programadores, como se describe en este artículo.  
  
 El registro refleja el orden en que se llamaron las APIs que alojan CLR.  También incluye datos útiles sobre el conjunto de runtimes instalados que se han detectado en el equipo.  El formato del registro de activación de CLR no está documentado, pero se puede utilizar para ayudar a los desarrolladores que necesitan resolver problemas de activación de CLR.  
  
> [!NOTE]
>  No se puede abrir un registro de activación hasta que el proceso que utiliza el CLR haya finalizado.  
  
> [!NOTE]
>  Los registros de activación de CLR no están localizados; siempre se generan en inglés.  
  
 En el siguiente ejemplo de un registro de activación, la información más útil está resaltada y se describe después del registro.  
  
```  
532,205950.367,CLR Loading log for C:\Tests\myapp.exe   
532,205950.367,Log started at 4:26:12 PM on 10/6/2011   
532,205950.367,-----------------------------------   
532,205950.382,FunctionCall: _CorExeMain   
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}   
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}   
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0   
532,205950.382,Input values for ComputeVersionString follow this line   
532,205950.382,-----------------------------------   
532,205950.382,Default Application Name: C:\Tests\myapp.exe   
532,205950.382,IsLegacyBind is: 0   
532,205950.382,IsCapped is 0   
532,205950.382,SkuCheckFlags are 0   
532,205950.382,ShouldEmulateExeLaunch is 0   
532,205950.382,LegacyBindRequired is 0   
532,205950.382,-----------------------------------   
532,205950.382,Parsing config file: C:\Tests\myapp.exe   
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727   
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.   
532,205950.398,SEM_FAILCRITICALERRORS is set to 0   
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3   
532,205950.398,FunctionCall: RealDllMain. Reason: 0   
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0  
  
```  
  
-   **CLR Loading log** proporciona la ruta de acceso al archivo ejecutable que inició el proceso que cargó el código administrado.  Observe que puede ser un host nativo.  
  
    ```  
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe  
  
    ```  
  
-   **Installed Runtime** es el conjunto de versiones de CLR instaladas en el equipo que son candidatas a la solicitud de activación.  
  
    ```  
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0  
  
    ```  
  
-   **built with version** es la versión de CLR que se usa   para compilar el archivo binario que se ha proporcionado a métodos tales como [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md).  
  
    ```  
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727  
  
    ```  
  
-   **feature\-on\-demand installation** hace referencia a habilitar .NET Framework 3.5 en Windows 8.  Para obtener más información acerca de los escenarios, consulte [Errores de inicialización de .NET Framework: Administrar la experiencia del usuario](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md).  
  
    ```  
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3  
  
    ```  
  
## Vea también  
 [Implementación](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [Cómo: Configurar una aplicación para admitir .NET Framework 4 o 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)