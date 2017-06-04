---
title: "Specifying an Entry Point | Microsoft Docs"
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
  - "EntryPoint field"
  - "platform invoke, attribute fields"
  - "attribute fields in platform invoke, EntryPoint"
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Specifying an Entry Point
Un punto de entrada identifica la ubicación de una función en un archivo DLL.  En un proyecto administrado, el nombre original o el punto de entrada ordinal de una función de destino identifica dicha función dentro de los límites de la interoperabilidad.  Además, puede asignarle otro nombre al punto de entrada, lo que supone en realidad un cambio de nombre de la función.  
  
 A continuación, se muestra una lista de las razones que pueden existir para desear cambiarle el nombre a una función de un archivo DLL:  
  
-   Para no utilizar nombres de función de la API que distinguen mayúsculas de minúsculas  
  
-   Para cumplir los estándares de nomenclatura existentes  
  
-   Para incluir funciones que toman tipos de datos distintos \(declarando varias versiones de la misma función de un archivo DLL\)  
  
-   Para simplificar el uso de las API que contienen versiones ANSI y Unicode  
  
 En este tema se muestra la forma de cambiar el nombre de una función de un archivo DLL en código administrado.  
  
## Cambiar el nombre de una función en Visual Basic  
 Visual Basic utiliza la palabra clave **Function** en la instrucción **Declare** para establecer el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName>.  En el siguiente ejemplo muestra una declaración básica.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 Es posible reemplazar el punto de entrada **MessageBox** por **MsgBox** incluyendo la palabra clave **Alias** en la definición, tal y como se muestra en el ejemplo siguiente.  En los dos ejemplos, la palabra clave **Auto** elimina la necesidad de especificar la versión del juego de caracteres del punto de entrada.  Para obtener más información acerca de la forma de seleccionar un juego de caracteres, vea [Especificar un juego de caracteres](../../../docs/framework/interop/specifying-a-character-set.md).  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## Cambiar el nombre de una función en C\# y C\+\+  
 Puede utilizar el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> para especificar una función DLL por nombre u ordinal.  Si el nombre de la función en la definición del método es el mismo que el punto de entrada en el archivo DLL, no es necesario identificar la función de forma explícita con el campo **EntryPoint**.  En caso contrario, utilice una de las siguientes formas de atributo para indicar un nombre u ordinal:  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 Tenga en cuenta que los ordinales deben ir precedidos del símbolo de libra esterlina \(\#\).  
  
 En el siguiente ejemplo se muestra la forma de reemplazar **MessageBoxA** por **MsgBox** en el código utilizando el campo **EntryPoint**.  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)