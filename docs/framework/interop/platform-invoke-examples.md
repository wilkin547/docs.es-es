---
title: "Platform Invoke Examples | Microsoft Docs"
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
  - "examples [.NET Framework], platform invoke"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "platform invoke, examples"
  - "interoperation with unmanaged code, platform invoke"
  - "DLL functions"
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Platform Invoke Examples
En los siguientes ejemplos se muestra la forma de definir la función **MessageBox** y de llamarla en User32.dll, pasando una cadena sencilla como argumento.  En los ejemplos, el campo [DllImportAttribute.CharSet Field](frlrfSystemRuntimeInteropServicesDllImportAttributeClassCharSetTopic) se establece en **Auto** para permitir que la plataforma de destino determine el ancho de los caracteres y el cálculo de referencias de cadenas.  
  
 El mismo ejemplo se muestra en Visual Basic, C\# y C\+\+.  Para que se muestren todos los lenguajes, haga clic en el botón Filtro de lenguaje ![](../../../docs/framework/interop/media/filter2.gif "Filter2") del ángulo superior izquierdo de la página.  Para obtener más ejemplos, vea [Cálculo de referencias de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md) &#124;  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
       ByVal caption As String, ByVal Typ As Integer) As IntPtr  
End Class  
  
Public Class HelloWorld      
    Public Shared Sub Main()  
        Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0)  
    End Sub  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
     [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern IntPtr MessageBox(int hWnd, String text,   
                     String caption, uint type);  
}  
  
public class HelloWorld {  
    public static void Main() {  
       Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0);  
    }  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" IntPtr MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
void main(void) {  
     String* pText = L"Hello World!";  
     String* pCaption = L"Platform Invoke Sample";  
     MessageBox(0, pText, pCaption, 0);  
}  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md)