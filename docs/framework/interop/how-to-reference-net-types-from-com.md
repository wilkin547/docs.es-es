---
title: 'Cómo: Hacer referencia a tipos de .NET desde COM'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0333cd73240e685b46917d85afe0876532db3fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-reference-net-types-from-com"></a>Cómo: Hacer referencia a tipos de .NET desde COM
Desde el punto de vista del código de cliente y servidor, las diferencias entre COM y .NET Framework son prácticamente inapreciables. Los clientes Microsoft Visual Basic pueden ver los objetos de .NET en el Examinador de objetos, que expone los métodos y la sintaxis, las propiedades, y los campos de los objetos exactamente del mismo modo que si se tratase de cualquier otro objeto COM.  
  
 El proceso de importación de una biblioteca de tipos es algo más complicado para los clientes C++, a pesar de que se utilizan las mismas herramientas para exportar los metadatos a una biblioteca de tipos COM. Para hacer referencia a miembros de objetos de .NET desde un cliente C++ no administrado, haga referencia al archivo TLB (generado con Tlbexp.exe) con la directiva **#import**. Cuando se hace referencia a una biblioteca de tipos desde C++, es necesario especificar la opción **raw_interfaces_only** o importar las definiciones de la biblioteca de clases base, Mscorlib.tlb.  
  
### <a name="to-import-a-library"></a>Para importar una biblioteca  
  
-   Especifique la opción **raw_interfaces_only** en la directiva **#import**. Por ejemplo:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     -o bien-  
  
-   Incluya una directiva #import para Mscorlib.tlb. Por ejemplo:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Exponer componentes de .NET Framework en COM](exposing-dotnet-components-to-com.md)  
 [Registrar ensamblados con COM](registering-assemblies-with-com.md)  
 [Llamar a un objeto de .NET](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))  
 [Implementar una aplicación para obtener acceso a COM](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))
