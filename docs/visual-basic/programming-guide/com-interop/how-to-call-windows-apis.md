---
title: 'Cómo: Llamar a las API de Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: de568c3273d4d040c6566136e5d59e2155b86f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643645"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Cómo: Llamar a las API de Windows (Visual Basic)
En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El método no es estático, es abstracto o se ha definido anteriormente. El tipo principal es una interfaz o la longitud de *nombre* o *nombre dll* es cero. (<xref:System.ArgumentException>)  
  
-   El *nombre* o *nombre dll* es `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Tipo contenedor que se ha creado anteriormente mediante `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vea también  
 [Aproximación a la invocación de plataforma](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [Ejemplos de invocación de plataforma](../../../framework/interop/platform-invoke-examples.md)  
 [Consumir funciones DLL no administradas](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [Definir un método con Reflection Emit](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
