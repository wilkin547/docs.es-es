---
title: "Ejecuci&#243;n en paralelo y en proceso | Microsoft Docs"
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
  - "ejecución en paralelo en el mismo proceso"
  - "ejecución en paralelo, en el mismo proceso"
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 25
---
# Ejecuci&#243;n en paralelo y en proceso
A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar el hospedaje en paralelo en el mismo proceso para ejecutar varias versiones de Common Language Runtime \(CLR\) en un único proceso.  De forma predeterminada, los componentes COM administrados se ejecutan con la versión de .NET Framework con la que se compilaron, sin tener en cuenta la versión de .NET Framework que está cargada para el proceso.  
  
## Fondo  
 .NET Framework siempre ha proporcionado hospedaje en paralelo para aplicaciones de código administrado, pero antes de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] no proporcionaba esa funcionalidad para componentes COM administrados.  En el pasado, los componentes COM administrados que se cargaban en un proceso se ejecutaban con la versión del runtime que ya estaba cargada o con la última versión instalada de .NET Framework.  Si esta versión no era compatible con el componente COM, se producía un error en el componente.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] proporciona un nuevo enfoque al hospedaje en paralelo que garantiza lo siguiente:  
  
-   La instalación de una nueva versión de .NET Framework no tiene ningún efecto en las aplicaciones existentes.  
  
-   Las aplicaciones se ejecutan con la versión de .NET Framework con la que se compilaron.  No utilizan la nueva versión de .NET Framework a menos que se indique expresamente.  Sin embargo, es más fácil para las aplicaciones realizar la transición a una nueva versión de .NET Framework.  
  
## Efectos en usuarios y desarrolladores  
  
-   **Usuarios finales y administradores del sistema**.  Estos usuarios ya pueden confiar en que la instalación de una nueva versión del runtime, ya sea de forma independiente o con una aplicación, no tendrá ningún impacto en sus equipos.  Las aplicaciones existentes continuarán ejecutándose como lo hacían antes.  
  
-   **Desarrolladores de aplicaciones**.  El hospedaje en paralelo no tiene casi ningún efecto en los desarrolladores de aplicaciones.  De forma predeterminada, las aplicaciones se ejecutan siempre con la versión de .NET Framework con la que se compilaron; esto no ha cambiado.  Sin embargo, los desarrolladores pueden invalidar este comportamiento y dirigir la aplicación para que se ejecute con una versión más reciente de .NET Framework \(vea [escenario 2](#scenarios)\).  
  
-   **Desarrolladores de bibliotecas y consumidores**.  El hospedaje en paralelo no resuelve los problemas de compatibilidad a los que se enfrentan los desarrolladores de bibliotecas.  Una biblioteca cargada directamente por una aplicación, mediante una referencia directa o una llamada <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>, continúa utilizando el runtime de <xref:System.AppDomain> en el que está cargada.  Debería probar las bibliotecas con todas las versiones de .NET Framework que desee admitir.  Si una aplicación está compilada mediante el runtime de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] pero incluye una biblioteca que se compiló mediante un runtime anterior, esa biblioteca también utilizará el runtime de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  Sin embargo, si tiene una aplicación que se compiló utilizando un runtime anterior y una biblioteca que se compiló mediante [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], debe forzar a su aplicación a utilizar igualmente [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] \(vea [escenario 3](#scenarios)\).  
  
-   **Desarrolladores de componentes COM administrados**.  En el pasado, los componentes COM administrados se ejecutaban automáticamente, mediante la última versión del runtime instalada en el equipo.  Ya puede ejecutar los componentes COM con la versión del runtime con la que se compilaron.  
  
     Como se muestra en la siguiente tabla, los componentes que se compilaron con la versión 1.1 de .NET Framework se pueden ejecutar en paralelo con componentes de la versión 4, pero no se pueden ejecutar con componentes de la versión 2.0, 3.0 o 3.5, porque el hospedaje en paralelo no está disponible para esas versiones.  
  
    |Versión de .NET Framework|1.1|2.0 \- 3.5|4|  
    |-------------------------------|---------|----------------|-------|  
    |1.1|No es aplicable|No|Sí|  
    |2.0 \- 3.5|No|No es aplicable|Sí|  
    |4|Sí|Sí|No es aplicable|  
  
> [!NOTE]
>  Las versiones 3.0 y 3.5 de .NET Framework se compilan de forma incremental en la versión 2.0 y no necesitan ejecutarse en paralelo.  Se trata inherentemente de la misma versión.  
  
<a name="scenarios"></a>   
## Escenarios de hospedaje en paralelo comunes  
  
-   **Escenario 1:** una aplicación nativa que utiliza componentes COM compilados con versiones anteriores de .NET Framework.  
  
     Versiones de .NET Framework instaladas: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] y todas las demás versiones de .NET Framework utilizadas por los componentes COM.  
  
     Lo que debe hacer: en este escenario, no haga nada.  Los componentes COM se ejecutarán con la versión de .NET Framework con la que se registraron.  
  
-   **Escenario 2**: una aplicación administrada compilada con [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] que prefiere ejecutar con [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], pero desea ejecutar en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] si la versión 2.0 no está presente.  
  
     Versiones de .NET Framework instaladas: una versión anterior de .NET Framework y [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     Qué hacer: En [archivo de configuración de la aplicación](../../../docs/framework/configure-apps/index.md) en el directorio de aplicaciones, use [\<inicio\> elemento](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) y [\<supportedRuntime\> elemento](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) establecidos como sigue:  
  
    ```  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   **Escenario 3:** una aplicación nativa que utiliza componentes COM compilados con versiones anteriores de .NET Framework y que desea ejecutar con [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     Versiones de .NET Framework instaladas: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
     Lo que debe hacer: en el archivo de configuración de la aplicación en el directorio de aplicaciones, use el elemento `<startup>` con el atributo `useLegacyV2RuntimeActivationPolicy` establecido en `true` y el elemento `<supportedRuntime>` establecido del modo siguiente:  
  
    ```  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## Ejemplo  
 En el siguiente ejemplo se muestra un host COM no administrado que está ejecutando un componente COM administrado mediante la versión de .NET Framework con la que se compiló el componente.  
  
 Para ejecutar el ejemplo, compile y registrar el siguiente componente COM administrado mediante [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].  Para registrar el componente, en el menú de **Project** , haga clic en **Propiedades**, haga clic en la pestaña de **Compilación** , y seleccione la casilla de **Registrar para interoperabilidad COM** .  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 Compile la siguiente aplicación C\+\+ no administrada, que activa el objeto COM creado en el ejemplo anterior.  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
  
```  
  
## Vea también  
 [Elemento \<startup\>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)   
 [\<supportedRuntime\> \(Elemento\)](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)