---
title: Pasar estructuras
description: Aprenda a pasar estructuras y clases a funciones no administradas. Obtenga información sobre el atributo StructLayoutAttribute, que se utiliza para definir tipos con formato.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
ms.openlocfilehash: eae28d6746cd89d98b659b9eb957f158e1319190
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620825"
---
# <a name="passing-structures"></a>Pasar estructuras
Muchas funciones no administradas esperan que el usuario pase, como parámetro de la función, miembros de estructuras (tipos definidos por el usuario en Visual Basic) o miembros de clases definidos en código administrado. Al pasar estructuras o clases al código no administrado mediante la invocación de plataforma, debe proporcionarse información adicional para mantener la distribución y alineación originales. En este tema se presenta el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>, que se utiliza para definir tipos con formato. Para estructuras y clases administradas, se puede seleccionar entre varios comportamientos de distribución previsibles que proporciona la enumeración **LayoutKind**.  
  
 Un punto fundamental de los conceptos presentados en este tema es la importante diferencia que hay entre los tipos de estructura y clase. Las estructuras son tipos de valor y las clases son tipos de referencia. Las clases siempre proporcionan al menos un nivel de direccionamiento indirecto de memoria (un puntero a un valor). Esta diferencia es importante porque las funciones no administradas exigen a menudo direccionamiento indirecto, como muestran los prototipos de la primera columna en la tabla siguiente. Las declaraciones administradas de estructura y clase de las columnas restantes muestran el grado hasta el que se puede ajustar el nivel de direccionamiento indirecto en la declaración. Se proporcionan declaraciones para Visual Basic y Visual C#.  
  
|Prototipo no administrado|Declaración administrada: <br />ningún direccionamiento indirecto<br />`Structure MyType`<br />`struct MyType;`|Declaración administrada: <br />uno nivel de direccionamiento indirecto<br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> No requiere ningún nivel de direccionamiento indirecto.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> No agrega ningún nivel de direccionamiento indirecto.|No es posible porque ya hay un nivel de direccionamiento indirecto.|  
|`DoWork(MyType* x);`<br /><br /> Requiere un nivel de direccionamiento indirecto.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Agrega un nivel de direccionamiento indirecto.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> No agrega ningún nivel de direccionamiento indirecto.|  
|`DoWork(MyType** x);`<br /><br /> Requiere dos niveles de direccionamiento indirecto.|No es posible porque no se puede usar **ByRef** **ByRef** o `ref` `ref`.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Agrega un nivel de direccionamiento indirecto.|  
  
 La tabla describe las siguientes directrices para las declaraciones de invocación de plataforma:  
  
- Utilice una estructura pasada por valor cuando la función no administrada no requiera direccionamiento indirecto.  
  
- Utilice una estructura pasada por referencia o una clase pasada por valor cuando la función no administrada requiera un nivel de direccionamiento indirecto.  
  
- Utilice una clase pasada por referencia cuando la función no administrada requiera dos niveles de direccionamiento indirecto.  
  
## <a name="declaring-and-passing-structures"></a>Declarar y pasar estructuras  
 En el siguiente ejemplo se muestra la forma de definir las estructuras `Point` y `Rect` en código administrado y la forma de pasar los tipos como parámetros a la función **PtInRect** en el archivo User32.dll. **PtInRect** tiene la siguiente firma no administrada:  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Tenga en cuenta que debe pasar la estructura Rect por referencia, ya que la función espera un puntero que seleccione el tipo RECT.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "user32.dll" (
        ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}
  
internal static class NativeMethods
{  
    [DllImport("User32.dll")]  
    internal static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a>Declarar y pasar clases  
 Los miembros de una clase pueden pasarse a una función no administrada de un archivo DLL, siempre que la clase tenga una distribución de miembro fija. En el ejemplo siguiente se muestra la forma de pasar miembros de la clase `MySystemTime`, que están definidos en orden secuencial, a **GetSystemTime** en el archivo User32.dll. **GetSystemTime** tiene la siguiente firma no administrada:  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 A diferencia de los tipos de valor, las clases siempre tienen al menos un nivel de direccionamiento indirecto.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Friend Class NativeMethods  
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        sysTime As MySystemTime)  
    Friend Declare Auto Function MessageBox Lib "User32.dll" (
        hWnd As IntPtr, lpText As String, lpCaption As String, uType As UInteger) As Integer  
End Class  
  
Public Class TestPlatformInvoke
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        NativeMethods.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;
    public ushort wMonth;  
    public ushort wDayOfWeek;
    public ushort wDay;
    public ushort wHour;
    public ushort wMinute;
    public ushort wSecond;
    public ushort wMilliseconds;
}  
internal static class NativeMethods
{  
    [DllImport("Kernel32.dll")]  
    internal static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet = CharSet.Auto)]  
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        NativeMethods.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Llamar a una función DLL](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
