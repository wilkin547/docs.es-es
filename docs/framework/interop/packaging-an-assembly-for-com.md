---
title: "Packaging an Assembly for COM | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "COM interop, packaging assemblies"
  - "packaging assemblies for COM"
  - "Tlbexp.exe"
  - "TypeLibConverter class"
  - ".NET Services Installation tool"
  - "Assembly Registration tool"
  - "Type Library Exporter"
  - "Reqsvcs.exe"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "interoperation with unmanaged code, packaging assemblies"
  - "COM interop, exposing COM components"
  - "Reqasm.exe"
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Packaging an Assembly for COM
Los programadores de COM pueden beneficiarse de la siguiente información acerca de los tipos administrados que piensan incluir en su aplicación:  
  
-   Una lista de tipos que las aplicaciones COM pueden consumir  
  
     Ciertos tipos administrados no son visibles para COM; otros son visibles pero no pueden crearse; y otros son visibles y pueden crearse.  Un ensamblado puede contener cualquier combinación de tipos visibles, no visibles, que pueden crearse y que no pueden crearse.  Para obtener un mejor resultado, identifique los tipos de un ensamblado que piensa exponer en COM, especialmente cuando dichos tipos sean un subconjunto de los tipos expuestos en .NET Framework.  
  
     Para obtener información adicional, vea [Calificar tipos de .NET para la interoperación](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
-   Instrucciones relativas al control de versiones  
  
     Las clases administradas que implementan la interfaz de clase \(una interfaz generada por la interoperabilidad COM\) están sometidas a restricciones del control de versiones.  
  
     Para obtener instrucciones sobre el uso de la interfaz de clase, vea [Presentar la interfaz de clase](http://msdn.microsoft.com/es-es/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
-   Instrucciones de implementación  
  
     Los ensamblados con nombre seguro y firmados por un editor pueden instalarse en la caché global de ensamblados.  Los ensamblados que no están firmados deben instalarse en el equipo del usuario como ensamblados privados.  
  
     Para obtener más información, vea [Consideraciones de seguridad de ensamblados](../../../docs/framework/app-domains/assembly-security-considerations.md).  
  
-   Inclusión de bibliotecas de tipos  
  
     La mayoría de los tipos requieren una biblioteca de tipos cuando una aplicación COM los consume.  La generación de una biblioteca de tipos es una tarea que puede realizar el usuario o que pueden realizar los programadores de COM.  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona las opciones siguientes para generar una biblioteca de tipos:  
  
    -   [Exportador de la biblioteca de tipos](#cpconpackagingassemblyforcomanchor1)  
  
    -   [Clase TypeLibConverter](#cpconpackagingassemblyforcomanchor2)  
  
    -   [Herramienta Registro de ensamblados](#cpconpackagingassemblyforcomanchor3)  
  
    -   [Herramienta Instalación de servicios de .NET](#cpconpackagingassemblyforcomanchor4)  
  
     Independientemente del mecanismo que se elija, sólo se incluirán en la biblioteca de tipos generada los tipos públicos definidos en el ensamblado proporcionado por el usuario.  
  
     Puede empaquetar una biblioteca de tipos como un archivo independiente o incrustarla como un archivo de recursos Win32 dentro de una aplicación .NET.  Microsoft Visual Basic 6.0 realiza esta tarea automáticamente; sin embargo, cuando utilice [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)], debe incrustar la biblioteca de tipos manualmente.  Para obtener instrucciones, vea [Cómo: Incrustar bibliotecas de tipos como recursos de Win32 en aplicaciones basadas en .NET](http://msdn.microsoft.com/es-es/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44).  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## Exportador de la biblioteca de tipos  
 El [Exportador de la biblioteca de tipos \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) es una herramienta de línea de comandos que convierte en una biblioteca de tipos COM las clases e interfaces contenidas en un ensamblado.  Una vez que la información sobre el tipo de la clase está disponible, los clientes COM pueden crear una instancia de la clase de .NET y llamar a los métodos de la instancia, del mismo modo que si se tratase de un objeto COM.  Tlbexp.exe convierte todo un ensamblado de una vez.  No se puede utilizar Tlbexp.exe para generar información de tipos correspondiente a un subconjunto de los tipos definidos en un ensamblado.  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## Clase TypeLibConverter  
 La clase <xref:System.Runtime.InteropServices.TypeLibConverter>, ubicada en el espacio de nombres **System.Runtime.Interop**, convierte las clases e interfaces de un ensamblado en una biblioteca de tipos COM.  Esta API genera la misma información de tipos que la herramienta Exportador de la biblioteca de tipos, descrita en la sección anterior.  
  
 La **clase TypeLibConverter** implementa la [interfaz ITypeLibConverter](frlrfSystemRuntimeInteropServicesITypeLibConverterClassTopic).  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## Herramienta Registro de ensamblados  
 La [herramienta Registro de ensamblados \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) puede generar y registrar una biblioteca de tipos cuando se aplica la opción **\/tlb:**.  Los clientes COM requieren que las bibliotecas de tipos se instalen en el Registro de Windows.  Sin esta opción, Regasm.exe sólo registra los tipos de un ensamblado, no la biblioteca de tipos.  El registro de los tipos de un ensamblado y el registro de una biblioteca de tipos son actividades distintas.  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## Herramienta Instalación de servicios de .NET  
 La [herramienta Instalación de servicios de .NET \(Regsvcs.exe\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md) agrega clases administradas a los servicios de componentes de Windows 2000 y combina varias tareas en una sola herramienta.  Además de cargar y registrar un ensamblado, Regsvcs.exe puede generar, registrar e instalar la biblioteca de tipos en una aplicación COM\+ 1.0 existente.  
  
## Vea también  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/es-es/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Consideraciones de seguridad sobre ensamblados](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe \(Type Library Exporter\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [How to: Embed Type Libraries as Win32 Resources in Applications](http://msdn.microsoft.com/es-es/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)