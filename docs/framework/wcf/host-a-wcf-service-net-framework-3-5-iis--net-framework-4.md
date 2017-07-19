---
title: "C&#243;mo: Hospedar un servicio WCF escrito con .NET Framework 3.5 en IIS que ejecuta .NET Framework 4 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# C&#243;mo: Hospedar un servicio WCF escrito con .NET Framework 3.5 en IIS que ejecuta .NET Framework 4
Al hospedar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] escrito con [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] en un equipo que ejecuta [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], puede obtener <xref:System.ServiceModel.ProtocolException> con el siguiente texto.  
  
```Output  
Excepción no controlada: System.ServiceModel.ProtocolException: El tipo de contenido texto/html; charset=utf -8 del mensaje de respuesta no coincide con el tipo de contenido del enlace (application/soap+xml; charset=utf-8).Si utiliza un codificador personalizado, asegúrese de que el método IsContentTypeSupported se implementa de forma correcta.Los primeros 1024 bytes de la respuesta fueron: '<html>  <head>    <title>El dominio de la aplicación o el grupo de aplicaciones está ejecutando la versión 4 o posterior de .NET Framework.Esto se puede producir si la configuración de IIS se ha establecido en 4.0 o posterior para esta aplicación web, o si está utilizando la versión 4.0 o posterior del servidor de desarrollo web de ASP.NET.El elemento <compilation> del archivo Web.config para esta aplicación web no contiene el atributo 'targetFrameworkMoniker' requerido para esta versión de .NET Framework (por ejemplo, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').Actualice el archivo Web.config con este atributo o configure la aplicación web para usar una versión diferente de .NET Framework.</title>...  
```  
  
 O bien, si intenta ir al archivo .svc del servicio, puede ver una página de error con el siguiente texto.  
  
```Output  
El dominio de la aplicación o el grupo de aplicaciones está ejecutando la versión 4.0 o posterior de .NET Framework.Esto se puede producir si la configuración de IIS se ha establecido en 4.0 o posterior para esta aplicación web, o si está utilizando la versión 4.0 o posterior del servidor de desarrollo web de ASP.NET.El elemento <compilation> del archivo Web.config para esta aplicación web no contiene el atributo 'targetFrameworkMoniker' requerido para esta versión de .NET Framework (por ejemplo, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').Actualice el archivo Web.config con este atributo o configure la aplicación web para utilizar una versión diferente de .NET Framework.  
```  
  
 Estos errores se producen porque el dominio de aplicación en el que se ejecuta IIS está ejecutando [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] y el servicio de WCF esperaba ejecutarse en [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].Este tema explica las modificaciones necesarias para hacer que el servicio se ejecute.  
  
 Luego, encuentre el elemento \<`compilers`\> y cambie la opción de proveedor de CompilerVersion para tener un valor de 4.0.De forma predeterminada, hay dos elementos \<`compiler`\> en el elemento \<`compilers`\>.Debe actualizar la opción de proveedor de CompilerVersion para ambos tal y como se muestra en el siguiente ejemplo.  
  
```  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### Adición del atributo targetFramework necesario  
  
1.  Abra el archivo Web.config del servicio y busque el elemento \<`compilation`\>.  
  
2.  Agregue el atributo `targetFramework` al elemento \<`compilation`\> tal y como se muestra en el siguiente ejemplo.  
  
    ```  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3.  Busque el elemento \<`compilers`\> y cambie la opción de proveedor de CompilerVersion para tener un valor de 4.0.De forma predeterminada, hay dos elementos \<`compiler`\> en el elemento \<`compilers`\>.Debe actualizar la opción de proveedor de CompilerVersion para ambos tal y como se muestra en el siguiente ejemplo.  
  
    ```  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```