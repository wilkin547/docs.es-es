---
title: Procedimiento para hacer referencia a tipos de .NET desde COM
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
ms.openlocfilehash: 0223cb25b933cc84af49aa86d90259fdf1fd3efc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124173"
---
# <a name="how-to-reference-net-types-from-com"></a>Procedimiento para hacer referencia a tipos de .NET desde COM
Desde el punto de vista del código de cliente y servidor, las diferencias entre COM y .NET Framework son prácticamente inapreciables. Los clientes Microsoft Visual Basic pueden ver los objetos de .NET en el Examinador de objetos, que expone los métodos y la sintaxis, las propiedades, y los campos de los objetos exactamente del mismo modo que si se tratase de cualquier otro objeto COM.  
  
 El proceso de importación de una biblioteca de tipos es algo más complicado para los clientes C++, a pesar de que se utilizan las mismas herramientas para exportar los metadatos a una biblioteca de tipos COM. Para hacer referencia a miembros de objetos de .NET desde un cliente C++ no administrado, haga referencia al archivo TLB (generado con Tlbexp.exe) con la directiva **#import**. Cuando se hace referencia a una biblioteca de tipos desde C++, es necesario especificar la opción **raw_interfaces_only** o importar las definiciones de la biblioteca de clases base, Mscorlib.tlb.  
  
### <a name="to-import-a-library"></a>Para importar una biblioteca  
  
- Especifique la opción **raw_interfaces_only** en la directiva **#import**. Por ejemplo:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     o bien  
  
- Incluya una directiva #import para Mscorlib.tlb. Por ejemplo:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>Vea también

- [Exponer componentes de .NET Framework en COM](exposing-dotnet-components-to-com.md)
- [Registrar ensamblados con COM](registering-assemblies-with-com.md)
- [Llamada a un objeto de .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Implementar una aplicación para obtener acceso a COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
