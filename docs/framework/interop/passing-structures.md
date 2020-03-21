---
title: Pasar estructuras
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
ms.openlocfilehash: 11e329fa8f0c059b6c2f1c8ccb1d6bd0d0f0030a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181338"
---
# <a name="passing-structures"></a><span data-ttu-id="79265-102">Pasar estructuras</span><span class="sxs-lookup"><span data-stu-id="79265-102">Passing Structures</span></span>
<span data-ttu-id="79265-103">Muchas funciones no administradas esperan que el usuario pase, como parámetro de la función, miembros de estructuras (tipos definidos por el usuario en Visual Basic) o miembros de clases definidos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="79265-103">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="79265-104">Al pasar estructuras o clases al código no administrado mediante la invocación de plataforma, debe proporcionarse información adicional para mantener la distribución y alineación originales.</span><span class="sxs-lookup"><span data-stu-id="79265-104">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="79265-105">En este tema se presenta el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>, que se utiliza para definir tipos con formato.</span><span class="sxs-lookup"><span data-stu-id="79265-105">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="79265-106">Para estructuras y clases administradas, se puede seleccionar entre varios comportamientos de distribución previsibles que proporciona la enumeración **LayoutKind**.</span><span class="sxs-lookup"><span data-stu-id="79265-106">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="79265-107">Un punto fundamental de los conceptos presentados en este tema es la importante diferencia que hay entre los tipos de estructura y clase.</span><span class="sxs-lookup"><span data-stu-id="79265-107">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="79265-108">Las estructuras son tipos de valor y las clases son tipos de referencia. Las clases siempre proporcionan al menos un nivel de direccionamiento indirecto de memoria (un puntero a un valor).</span><span class="sxs-lookup"><span data-stu-id="79265-108">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="79265-109">Esta diferencia es importante porque las funciones no administradas exigen a menudo direccionamiento indirecto, como muestran los prototipos de la primera columna en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="79265-109">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="79265-110">Las declaraciones administradas de estructura y clase de las columnas restantes muestran el grado hasta el que se puede ajustar el nivel de direccionamiento indirecto en la declaración. Se proporcionan declaraciones para Visual Basic y Visual C#.</span><span class="sxs-lookup"><span data-stu-id="79265-110">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="79265-111">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="79265-111">Unmanaged signature</span></span>|<span data-ttu-id="79265-112">Declaración administrada:</span><span class="sxs-lookup"><span data-stu-id="79265-112">Managed declaration:</span></span> <br /><span data-ttu-id="79265-113">ningún direccionamiento indirecto</span><span class="sxs-lookup"><span data-stu-id="79265-113">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="79265-114">Declaración administrada:</span><span class="sxs-lookup"><span data-stu-id="79265-114">Managed declaration:</span></span> <br /><span data-ttu-id="79265-115">uno nivel de direccionamiento indirecto</span><span class="sxs-lookup"><span data-stu-id="79265-115">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="79265-116">No requiere ningún nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-116">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="79265-117">No agrega ningún nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-117">Adds zero levels of indirection.</span></span>|<span data-ttu-id="79265-118">No es posible porque ya hay un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-118">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="79265-119">Requiere un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-119">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="79265-120">Agrega un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-120">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="79265-121">No agrega ningún nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-121">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="79265-122">Requiere dos niveles de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-122">Demands two levels of indirection.</span></span>|<span data-ttu-id="79265-123">No es posible porque no se puede usar **ByRef** **ByRef** ni `ref` `ref`.</span><span class="sxs-lookup"><span data-stu-id="79265-123">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="79265-124">Agrega un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-124">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="79265-125">La tabla describe las siguientes directrices para las declaraciones de invocación de plataforma:</span><span class="sxs-lookup"><span data-stu-id="79265-125">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
- <span data-ttu-id="79265-126">Utilice una estructura pasada por valor cuando la función no administrada no requiera direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-126">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
- <span data-ttu-id="79265-127">Utilice una estructura pasada por referencia o una clase pasada por valor cuando la función no administrada requiera un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-127">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
- <span data-ttu-id="79265-128">Utilice una clase pasada por referencia cuando la función no administrada requiera dos niveles de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-128">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="79265-129">Declarar y pasar estructuras</span><span class="sxs-lookup"><span data-stu-id="79265-129">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="79265-130">En el siguiente ejemplo se muestra la forma de definir las estructuras `Point` y `Rect` en código administrado y la forma de pasar los tipos como parámetros a la función **PtInRect** en el archivo User32.dll.</span><span class="sxs-lookup"><span data-stu-id="79265-130">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="79265-131">**PtInRect** tiene la siguiente firma no administrada:</span><span class="sxs-lookup"><span data-stu-id="79265-131">**PtInRect** has the following unmanaged signature:</span></span>  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="79265-132">Tenga en cuenta que debe pasar la estructura Rect por referencia, ya que la función espera un puntero que seleccione el tipo RECT.</span><span class="sxs-lookup"><span data-stu-id="79265-132">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
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
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="79265-133">Declarar y pasar clases</span><span class="sxs-lookup"><span data-stu-id="79265-133">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="79265-134">Los miembros de una clase pueden pasarse a una función no administrada de un archivo DLL, siempre que la clase tenga una distribución de miembro fija.</span><span class="sxs-lookup"><span data-stu-id="79265-134">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="79265-135">En el ejemplo siguiente se muestra la forma de pasar miembros de la clase `MySystemTime`, que están definidos en orden secuencial, a **GetSystemTime** en el archivo User32.dll.</span><span class="sxs-lookup"><span data-stu-id="79265-135">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="79265-136">**GetSystemTime** tiene la siguiente firma no administrada:</span><span class="sxs-lookup"><span data-stu-id="79265-136">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="79265-137">A diferencia de los tipos de valor, las clases siempre tienen al menos un nivel de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="79265-137">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="79265-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79265-138">See also</span></span>

- [<span data-ttu-id="79265-139">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="79265-139">Calling a DLL Function</span></span>](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
