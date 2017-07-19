---
title: "Specifying a Character Set | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "platform invoke, attribute fields"
  - "attribute fields in platform invoke, CharSet"
  - "CharSet field"
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Specifying a Character Set
El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> controla el cálculo de referencias a cadenas y determina la manera en que la invocación de plataforma encuentra nombres de función en un archivo DLL.  En este tema se describen ambos comportamientos.  
  
 Ciertas API exportan dos versiones de las funciones que toman argumentos de cadena: caracteres de un byte \(ANSI\) y caracteres de dos bytes \(Unicode\).  La API Win32, por ejemplo, contiene los siguientes nombres de punto de entrada para la función **MessageBox**:  
  
-   **MessageBoxA**  
  
     Proporciona formato ANSI de caracteres de 1 byte, que se distingue por una "A" agregada al nombre del punto de entrada.  Las llamadas a **MessageBoxA** siempre calculan las referencias a cadenas en formato ANSI, como ocurre en las plataformas Windows 95 y Windows 98.  
  
-   **MessageBoxW**  
  
     Proporciona formato Unicode de caracteres de 2 bytes, que se distingue por una "W" agregada al nombre del punto de entrada.  Las llamadas a **MessageBoxW** siempre calculan las referencias a cadenas en formato Unicode, como ocurre en las plataformas Windows NT y Windows 2000.  
  
## Cálculo de referencias a cadenas y coincidencia de nombres  
 El campo **CharSet** acepta los siguientes valores:  
  
 **CharSet.Ansi** \(valor predeterminado\)  
  
-   Cálculo de referencias a cadenas  
  
     La invocación de plataforma calcula las referencias a cadenas desde su formato administrado \(Unicode\) al formato ANSI.  
  
-   Coincidencia de nombres  
  
     Cuando el campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName> es **true** \(valor predeterminado en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]\), la invocación de plataforma sólo busca el nombre que se especifica.  Por ejemplo, si se especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error cuando no se encuentra exactamente esta grafía.  
  
     Cuando el valor del campo **ExactSpelling** es **false**, como lo es de forma predeterminada en C\+\+ y C\#, la invocación de plataforma busca primero el nombre sin el sufijo \(**MessageBox**\) y, a continuación, el nombre con el sufijo \(**MessageBoxA**\) si no se encuentra el anterior.  Tenga en cuenta que el comportamiento de coincidencia del nombre ANSI se diferencia del comportamiento de coincidencia del nombre Unicode.  
  
 **CharSet.Unicode**  
  
-   Cálculo de referencias a cadenas  
  
     La invocación de plataforma copia las cadenas de su formato administrado \(Unicode\) al formato Unicode.  
  
-   Coincidencia de nombres  
  
     Cuando el campo **ExactSpelling** es **true** \(valor predeterminado en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]\), la invocación de plataforma sólo busca el nombre que se especifica.  Por ejemplo, si se especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error cuando no se encuentra exactamente esta grafía.  
  
     Cuando el valor del campo **ExactSpelling** es **false**, como lo es de forma predeterminada en C\+\+ y C\#, la invocación de plataforma busca primero el nombre con el sufijo \(**MessageBoxW**\) y, a continuación, el nombre sin el sufijo \(**MessageBox**\) si no se encuentra el anterior.  Tenga en cuenta que el comportamiento de coincidencia del nombre UNICODE, se diferencia del comportamiento de coincidencia del nombre ANSI.  
  
 **CharSet.Auto**  
  
-   La invocación de plataforma elige uno de los dos formatos, ANSI o Unicode, en tiempo de ejecución, basándose en la plataforma de destino.  
  
## Especificar un juego de caracteres en Visual Basic  
 El siguiente ejemplo declara la función **MessageBox** tres veces, cada vez con un comportamiento de juego de caracteres diferente.  Se puede especificar el comportamiento de juego de caracteres en Visual Basic agregando las palabras clave **Ansi**, **Unicode** o **Auto** a la instrucción de declaración.  
  
 Si se omite la palabra clave del juego de caracteres, tal como se hace en la primera instrucción de declaración, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> utiliza de forma predeterminada el juego de caracteres ANSI.  Las instrucciones segunda y tercera del ejemplo especifican explícitamente un juego de caracteres con una palabra clave.  
  
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
  
## Especificar un juego de caracteres en C\# y C\+\+  
 El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> identifica el juego de caracteres subyacente como ANSI o Unicode.  El juego de caracteres controla la forma en que deben calcularse las referencias a los argumentos de cadena para un método.  Utilice una de los formatos siguientes para indicar el juego de caracteres:  
  
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
  
 En el siguiente ejemplo se muestran tres definiciones administradas de la función **MessageBox** con atributos para especificar un juego de caracteres.  En la primera definición, como se omite, el campo **CharSet** toma como valor predeterminado el juego de caracteres ANSI.  
  
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
  
## Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)