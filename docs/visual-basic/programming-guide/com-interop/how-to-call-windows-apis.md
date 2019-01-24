---
title: Procedimiento Llamar a las API de Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 5db6e299012982024f34d46906de1a3be9b20ff1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650708"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Procedimiento Llamar a las API de Windows (Visual Basic)
En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El método no es estático, es abstracto o se ha definido anteriormente. El tipo primario es una interfaz o la longitud de *nombre* o *dllName* es cero. (<xref:System.ArgumentException>)  
  
-   El *nombre* o *dllName* es `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Tipo contenedor que se ha creado anteriormente mediante `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vea también

- [Aproximación a la invocación de plataforma](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Ejemplos de invocación de plataforma](../../../framework/interop/platform-invoke-examples.md)
- [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definir un método con Reflection Emit](https://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
