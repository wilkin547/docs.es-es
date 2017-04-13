---
title: "How to: Reference .NET Types from COM | Microsoft Docs"
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
  - "importing type library"
  - "COM interop, referencing .NET types"
  - "interoperation with unmanaged code, referencing .NET types"
  - "referencing .NET types"
  - "interoperation with unmanaged code, importing type library"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Reference .NET Types from COM
Desde el punto de vista del código de cliente y servidor, las diferencias entre COM y .NET Framework son prácticamente inapreciables.  Los clientes Microsoft Visual Basic pueden ver los objetos de .NET en el Examinador de objetos, que expone los métodos y la sintaxis, las propiedades, y los campos de los objetos exactamente del mismo modo que si se tratase de cualquier otro objeto COM.  
  
 El proceso de importación de una biblioteca de tipos es algo más complicado para los clientes C\+\+, a pesar de que se utilizan las mismas herramientas para exportar los metadatos a una biblioteca de tipos COM.  Para hacer referencia a miembros de objetos de .NET desde un cliente C\+\+ no administrado, haga referencia al archivo TLB \(generado con Tlbexp.exe\) con la directiva **\#import**.  Cuando se hace referencia a una biblioteca de tipos desde C\+\+, es necesario especificar la opción **raw\_interfaces\_only** o importar las definiciones de la biblioteca de clases base, Mscorlib.tlb.  
  
### Para importar una biblioteca  
  
-   Especifique la opción **raw\_interfaces\_only** en la directiva **\#import**.  Por ejemplo:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     O bien  
  
-   Incluya una directiva \#import para Mscorlib.tlb.  Por ejemplo:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## Vea también  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/es-es/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/es-es/fb63564c-c1b9-4655-a094-a235625882ce)