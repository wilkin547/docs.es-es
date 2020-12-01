---
title: Ejemplo MsgBox
description: Vea un ejemplo de cómo pasar tipos de cadena por valores como parámetros In con MsgBox. Muestra cuándo usar los campos EntryPoint, CharSet y ExactSpelling en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
ms.openlocfilehash: 024ed612115ce73646596651fe454238418446db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242024"
---
# <a name="msgbox-sample"></a>Ejemplo MsgBox

En este ejemplo se muestra cómo pasar tipos de cadena por valor como parámetros In y cuándo utilizar los campos <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> y <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 En el ejemplo MsgBox se utiliza la siguiente función no administrada, que se muestra con su declaración de función original:  
  
- **MessageBox** exportada desde User32.dll.  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,
       UINT uType);  
    ```  
  
 En este ejemplo, la clase `NativeMethods` contiene un prototipo administrado para cada función no administrada a la que se llama desde la clase `MsgBoxSample`. Los métodos de prototipo administrados `MsgBox`, `MsgBox2` y `MsgBox3` tienen declaraciones diferentes para la misma función no administrada.  
  
 La declaración para `MsgBox2` produce una salida incorrecta en el cuadro de mensaje porque el tipo de caracteres, especificado como ANSI, no corresponde con el punto de entrada `MessageBoxW`, que es el nombre de la función Unicode. La declaración de `MsgBox3` genera una falta de coincidencia entre los campos **EntryPoint**, **CharSet** y **ExactSpelling**. Al llamar a `MsgBox3`, se produce una excepción. Para obtener información detallada sobre los nombres de cadena y la serialización de nombres, vea [Especificar un juego de caracteres](specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Declaración de prototipos  

 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Llamadas a funciones  

 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Serialización de cadenas](marshaling-strings.md)
- [Serialización predeterminada para cadenas](default-marshaling-for-strings.md)
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
- [Especificar un juego de caracteres](specifying-a-character-set.md)
