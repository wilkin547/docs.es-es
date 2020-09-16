---
title: Procedimiento Llamadas a las API de Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 863986e94855e02e9fd04685f7dc3e8e7f7b1cc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548070"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Cómo: Llamar a las API de Windows (Visual Basic)
En este ejemplo se define y `MessageBox` se llama a la función en user32.dll y, a continuación, se le pasa una cadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- El método no es estático, es abstracto o se ha definido previamente. El tipo primario es una interfaz o la longitud del *nombre* o *DllName* es cero. (<xref:System.ArgumentException>)  
  
- El *nombre* o *DllName* es `Nothing` . (<xref:System.ArgumentNullException>)  
  
- Tipo contenedor que se ha creado anteriormente mediante `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vea también

- [Aproximación a la invocación de plataforma](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Ejemplos de invocación de plataforma](../../../framework/interop/platform-invoke-examples.md)
- [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definir un método con la emisión de la reflexión](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Tutorial: Llamadas a las API de Windows](walkthrough-calling-windows-apis.md)
- [Interoperabilidad COM](index.md)
