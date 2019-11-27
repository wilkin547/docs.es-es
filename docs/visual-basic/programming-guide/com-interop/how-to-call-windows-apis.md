---
title: 'Cómo: Llamar a las API de Windows'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 6f3c53243d7aeb73be81796d5ca185c3a3c41c72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348711"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Cómo: Llamar a las API de Windows (Visual Basic)
En este ejemplo se define y se llama a la función `MessageBox` en user32. dll y, a continuación, se le pasa una cadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- El método no es estático, es abstracto o se ha definido previamente. El tipo primario es una interfaz o la longitud del *nombre* o *DllName* es cero. (<xref:System.ArgumentException>)  
  
- El *nombre* o *DllName* es `Nothing`. (<xref:System.ArgumentNullException>)  
  
- Tipo contenedor que se ha creado anteriormente mediante `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vea también

- [Aproximación a la invocación de plataforma](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Ejemplos de invocación de plataforma](../../../framework/interop/platform-invoke-examples.md)
- [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definir un método con la emisión de la reflexión](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
