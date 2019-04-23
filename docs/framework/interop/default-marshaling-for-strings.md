---
title: Cálculo de referencias predeterminado para cadenas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47543056eaa538b008db3332dda776c0f300108d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078478"
---
# <a name="default-marshaling-for-strings"></a>Cálculo de referencias predeterminado para cadenas
Las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> tienen un comportamiento de serialización similar.  
  
 Las referencias de las cadenas se calculan como un tipo `BSTR` de estilo COM o como una cadena terminada en NULL (una matriz de caracteres que termina con un carácter NULL). Las referencias de los caracteres dentro de la cadena se pueden calcular como ANSI o Unicode (el valor predeterminado en los sistemas Windows).  
  
 En este tema se proporciona la siguiente información sobre el cálculo de referencias de tipos de cadena:  
  
-   [Cadenas usadas en interfaces](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [Cadenas usadas en la invocación de plataforma](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [Cadenas usadas en estructuras](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [Búferes de cadenas de longitud fija](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a>Cadenas usadas en interfaces  
 En la siguiente tabla se muestran las opciones de cálculo de referencias para el tipo de datos de cadena cuando las referencias se calculan como un argumento de método a código no administrado. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a interfaces COM.  
  
|Tipo de enumeración|Descripción de formato no administrado|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr` (valor predeterminado)|`BSTR` de estilo COM con una longitud fija y caracteres Unicode.|  
|`UnmanagedType.LPStr`|Puntero a una matriz de caracteres Unicode terminada en NULL.|  
|`UnmanagedType.LPWStr`|Puntero a una matriz de caracteres Unicode terminada en null.|  
  
 Esta tabla se aplica a cadenas. Sin embargo, para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `UnmanagedType.LPStr` y `UnmanagedType.LPWStr`.  
  
 En el ejemplo siguiente se muestran las cadenas declaradas en la interfaz `IStringWorker`.  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

En el ejemplo siguiente se muestra la interfaz correspondiente descrita en una biblioteca de tipos.

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a>Cadenas usadas en la plataforma de invocación  
 La invocación de plataforma copia los argumentos de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado de la plataforma. Las cadenas son inmutables y no se vuelven a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la llamada.  
  
 En la tabla siguiente se enumeran las opciones de cálculo de referencias cuando las referencias de cadenas se calculan como un argumento de método de una llamada de invocación de plataforma. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas.  
  
|Tipo de enumeración|Descripción de formato no administrado|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|`BSTR` de estilo COM con una longitud fija y caracteres ANSI.|  
|`UnmanagedType.BStr`|`BSTR` de estilo COM con una longitud fija y caracteres Unicode.|  
|`UnmanagedType.LPStr`|Puntero a una matriz de caracteres Unicode terminada en NULL.|  
|`UnmanagedType.LPTStr`|Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.|  
|`UnmanagedType.LPWStr`|Puntero a una matriz de caracteres Unicode terminada en null.|  
|`UnmanagedType.TBStr`|`BSTR` de estilo COM con una longitud fija y caracteres dependientes de la plataforma.|  
|`VBByRefStr`|Un valor que permite a Visual Basic .NET cambiar una cadena del código no administrado y reflejar los resultados en el código administrado. Este valor solo se admite con la invocación de plataforma. Este es el valor predeterminado en Visual Basic para las cadenas `ByVal`.|  
  
 Esta tabla se aplica a cadenas. Sin embargo, para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `LPStr`, `LPTStr` y `LPWStr`.  
  
 La siguiente definición de tipo muestra el uso correcto de `MarshalAsAttribute` para llamadas de invocación de plataforma.  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a>Cadenas usadas en estructuras  
 Las cadenas son miembros válidos de las estructuras; sin embargo, los búferes <xref:System.Text.StringBuilder> no son válidos en las estructuras. En la siguiente tabla se muestran las opciones de cálculo de referencias para el tipo de datos de cadena cuando las referencias del tipo se calculan como un campo. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a un campo.  
  
|Tipo de enumeración|Descripción de formato no administrado|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|`BSTR` de estilo COM con una longitud fija y caracteres Unicode.|  
|`UnmanagedType.LPStr`|Puntero a una matriz de caracteres Unicode terminada en NULL.|  
|`UnmanagedType.LPTStr`|Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.|  
|`UnmanagedType.LPWStr`|Puntero a una matriz de caracteres Unicode terminada en null.|  
|`UnmanagedType.ByValTStr`|Una matriz de longitud fija de caracteres; el tipo de la matriz se determina por el juego de caracteres de la estructura contenedora.|  
  
 El tipo `ByValTStr` se usa para matrices de caracteres de longitud fija insertadas que aparecen dentro de una estructura. Otros tipos se aplican a referencias de cadenas incluidas en estructuras que contienen punteros a cadenas.  
  
 El argumento `CharSet` del atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> que se aplica a la estructura contenedora determina el formato de carácter de las cadenas en las estructuras. Las siguientes estructuras de ejemplo contienen referencias de cadena y cadenas insertadas, así como caracteres ANSI, Unicode y dependientes de la plataforma.  
  
### <a name="type-library-representation"></a>Representación de la biblioteca de tipos  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 En el ejemplo de código siguiente se muestra cómo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para definir la misma estructura en diferentes formatos.  
  
```vb  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _  
Structure StringInfoA  
<MarshalAs(UnmanagedType.LPStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _  
Structure StringInfoW  
<MarshalAs(UnmanagedType.LPWStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
<MarshalAs(UnmanagedType.BStr)> Public f3 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _  
Structure StringInfoT  
<MarshalAs(UnmanagedType.LPTStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a>Búferes de cadenas de longitud fija  
 En algunas circunstancias, se debe pasar un búfer de caracteres de longitud fija a código no administrado para su manipulación. En este caso no basta con pasar una cadena porque el destinatario no puede modificar el contenido del búfer que se pasa. Aunque la cadena se pase por referencia, no hay ninguna manera de inicializar el búfer con un tamaño determinado.  
  
 La solución consiste en pasar un búfer <xref:System.Text.StringBuilder> como argumento en lugar de una cadena. El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`. También puede inicializarse con una longitud fija. Por ejemplo, si inicializa un búfer `StringBuilder` con una capacidad de `N`, el contador de referencias proporcionará un búfer con un tamaño de (`N`+ 1) caracteres. + 1 tiene en cuenta el hecho de que la cadena no administrada tiene un terminador NULL mientras que `StringBuilder` no.  
  
 Por ejemplo, la función `GetWindowText` de la API de Microsoft Windows (definida en Windows.h) es un búfer de caracteres de longitud fija que debe pasarse a código no administrado para su manipulación. `LpString` apunta a un búfer asignado por el llamador de tamaño `nMaxCount`. Se espera que el llamador asigne el búfer y establezca el argumento `nMaxCount` en el tamaño del búfer asignado. El siguiente código muestra la declaración de función `GetWindowText`, tal y como se define en Windows.h.  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`. En el ejemplo de código siguiente se muestra cómo inicializar `StringBuilder` con una longitud fija.  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Comportamiento predeterminado del cálculo de referencias](default-marshaling-behavior.md)
- [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)
- [Atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Copiar y fijar](copying-and-pinning.md)
