---
title: Procedimiento para hacer referencia a tipos de .NET desde COM
description: Referencia a tipos de .NET desde COM Los clientes de VB pueden ver un objeto .NET en el examinador de objetos, pero los clientes de C++ deben hacer referencia a un archivo TLB con la \#directiva de importación.
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
ms.openlocfilehash: 4e6e9f13364241517167c341a04883a199e9d6c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267031"
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
- [Llamada a un objeto de .NET](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Implementar una aplicación para obtener acceso a COM](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
