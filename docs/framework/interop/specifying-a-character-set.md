---
title: Especificar un juego de caracteres
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e97c640472156c1a47ad125bffeaf39b8eb0762
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-a-character-set"></a>Especificar un juego de caracteres
El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controla la serialización de cadenas y determina cómo la invocación de plataforma busca nombres de función en un archivo DLL. En este tema se describen ambos comportamientos.  
  
 Algunas API exportan dos versiones de las funciones que toman argumentos de cadena: la versión estrecha (ANSI) y la versión ancha (Unicode). La API Win32, por ejemplo, incluye los siguientes nombres de punto de entrada para la función **MessageBox**:  
  
-   **MessageBoxA**  
  
     Proporciona el formato ANSI de caracteres de 1 byte, que se distingue por una "A" anexada al nombre del punto de entrada. Las llamadas a **MessageBoxA** siempre serializan las cadenas en formato ANSI, como es habitual en las plataformas Windows 95 y Windows 98.  
  
-   **MessageBoxW**  
  
     Proporciona el formato Unicode de caracteres de 2 bytes, que se distingue por una "W" anexada al nombre del punto de entrada. Las llamadas a **MessageBoxW** siempre serializan las cadenas en formato Unicode, como es habitual en las plataformas Windows NT, Windows 2000 y Windows XP.  
  
## <a name="string-marshaling-and-name-matching"></a>Serialización de cadenas y coincidencia de nombres  
 El campo **CharSet** acepta los valores siguientes:  
  
 **CharSet.Ansi** (valor predeterminado)  
  
-   Serialización de cadenas  
  
     La invocación de plataforma serializa las cadenas del formato administrado (Unicode) al formato ANSI.  
  
-   Coincidencia de nombres  
  
     Cuando el campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> es **true**, como sucede de forma predeterminada en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], la invocación de plataforma solo busca el nombre que especifique. Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.  
  
     Si el campo **ExactSpelling** es **false**, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias no alterado (**MessageBox**) y, luego, el nombre alterado (**MessageBoxA**) en el caso de que no se encuentre el alias no alterado. Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato ANSI difiere del comportamiento de la coincidencia de nombres en formato Unicode.  
  
 **CharSet.Unicode**  
  
-   Serialización de cadenas  
  
     La invocación de plataforma copia las cadenas del formato administrado (Unicode) al formato Unicode.  
  
-   Coincidencia de nombres  
  
     Cuando el campo **ExactSpelling** es **true**, como sucede de forma predeterminada en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], la invocación de plataforma solo busca el nombre que especifique. Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.  
  
     Si el campo **ExactSpelling** es **false**, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias alterado (**MessageBoxW**) y, luego, el nombre no alterado (**MessageBox**) en el caso de que no se encuentre el alias alterado. Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato Unicode difiere del comportamiento de la coincidencia de nombres en formato ANSI.  
  
 **CharSet.Auto**  
  
-   La invocación de plataforma elige entre los formatos ANSI y Unicode en tiempo de ejecución en función de la plataforma de destino.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Especificar un juego de caracteres en Visual Basic  
 En el ejemplo siguiente se declara la función **MessageBox** tres veces, cada una de ellas con un comportamiento de juego de caracteres diferente. Para especificar un comportamiento de juego de caracteres en Visual Basic, agregue la palabra clave **Ansi**, **Unicode** o **Auto** a la instrucción de declaración.  
  
 Si omite la palabra clave del juego de caracteres, tal y como se hace en la primera instrucción de la declaración, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> establece como valor predeterminado el juego de caracteres ANSI. En la segunda y tercera instrucciones del ejemplo se especifica explícitamente un juego de caracteres con una palabra clave.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Especificar un juego de caracteres en C# y C++  
 El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica el juego de caracteres subyacente como ANSI o Unicode. El juego de caracteres controla cómo se deben serializar los argumentos de cadena en un método. Use uno de los formatos siguientes para indicar el juego de caracteres:  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 En el ejemplo siguiente se muestran tres definiciones administradas de la función **MessageBox** con atributos para especificar un juego de caracteres. En la primera definición, debido a su omisión, el campo **CharSet** establece como valor predeterminado el juego de caracteres ANSI.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Crear prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Ejemplos de invocación de plataforma](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Serialización de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
