---
title: Ejemplo MsgBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f6ef3407c5f06e04d7a8b882a6458f236886dea
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="msgbox-sample"></a>Ejemplo MsgBox
En este ejemplo se muestra cómo pasar tipos de cadena por valor como parámetros In y cuándo utilizar los campos <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> y <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 En el ejemplo MsgBox se utiliza la siguiente función no administrada, que se muestra con su declaración de función original:  
  
-   **MessageBox** exportada desde User32.dll.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 En este ejemplo, la clase `LibWrap` contiene un prototipo administrado para cada función no administrada a la que se llama desde la clase `MsgBoxSample`. Los métodos de prototipo administrados `MsgBox`, `MsgBox2` y `MsgBox3` tienen declaraciones diferentes para la misma función no administrada.  
  
 La declaración para `MsgBox2` produce una salida incorrecta en el cuadro de mensaje porque el tipo de caracteres, especificado como ANSI, no corresponde con el punto de entrada `MessageBoxW`, que es el nombre de la función Unicode. La declaración de `MsgBox3` genera una falta de coincidencia entre los campos **EntryPoint**, **CharSet** y **ExactSpelling**. Al llamar a `MsgBox3`, se produce una excepción. Para obtener información detallada sobre los nombres de cadena y la serialización de nombres, vea [Especificar un juego de caracteres](../../../docs/framework/interop/specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Declaración de prototipos  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)] [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)] [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Llamadas a funciones  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)] [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)] [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 [Serialización de cadenas](../../../docs/framework/interop/marshaling-strings.md)   
 [Tipos de datos de invocación de plataforma](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Serialización predeterminada para cadenas](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [Creación de prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Especificar un juego de caracteres](../../../docs/framework/interop/specifying-a-character-set.md)

