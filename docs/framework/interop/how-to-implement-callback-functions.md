---
title: Procedimiento para implementar funciones de devolución de llamada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0a033e6881f9c0c8741fda26211b0f565762de4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331330"
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="9f94e-102">Procedimiento para implementar funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="9f94e-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="9f94e-103">El procedimiento y el ejemplo siguiente muestran cómo una aplicación administrada, mediante la invocación de la plataforma, puede imprimir el valor del identificador de cada ventana en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="9f94e-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="9f94e-104">En concreto, el uso del procedimiento y el ejemplo usan la función **EnumWindows** para recorrer la lista de ventanas y una función de devolución de llamada administrada (denominada CallBack) para imprimir el valor del identificador de ventana.</span><span class="sxs-lookup"><span data-stu-id="9f94e-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="9f94e-105">Para implementar una función de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="9f94e-105">To implement a callback function</span></span>  
  
1. <span data-ttu-id="9f94e-106">Observe la firma de la función **EnumWindows** antes de continuar con la implementación.</span><span class="sxs-lookup"><span data-stu-id="9f94e-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="9f94e-107">**EnumWindows** tiene la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="9f94e-107">**EnumWindows** has the following signature:</span></span>  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     <span data-ttu-id="9f94e-108">Una pista para saber que esta función requiere una devolución de llamada es la presencia del argumento **lpEnumFunc**.</span><span class="sxs-lookup"><span data-stu-id="9f94e-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="9f94e-109">Es habitual ver el prefijo **lp** (puntero largo) combinado con el sufijo **Func** en el nombre de los argumentos con un puntero a una función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9f94e-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="9f94e-110">Para consultar documentación acerca de las funciones de Win32, consulte Microsoft Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="9f94e-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2. <span data-ttu-id="9f94e-111">Cree la función de devolución de llamada administrada.</span><span class="sxs-lookup"><span data-stu-id="9f94e-111">Create the managed callback function.</span></span> <span data-ttu-id="9f94e-112">En el ejemplo, se declara un tipo de delegado, denominado `CallBack`, que toma dos argumentos (**hwnd** y **lparam**).</span><span class="sxs-lookup"><span data-stu-id="9f94e-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="9f94e-113">El primer argumento es un identificador de la ventana. El segundo argumento está definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9f94e-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="9f94e-114">En esta versión, ambos argumentos deben ser números enteros.</span><span class="sxs-lookup"><span data-stu-id="9f94e-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="9f94e-115">Generalmente, las funciones de devolución de llamada devuelven valores distintos de cero para indicar que se ha realizado correctamente y cero para indicar que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="9f94e-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="9f94e-116">En este ejemplo, el valor devuelto se establece explícitamente en **true** para continuar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="9f94e-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3. <span data-ttu-id="9f94e-117">Cree un delegado y páselo como argumento a la función **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="9f94e-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="9f94e-118">La invocación de la plataforma convierte automáticamente el delegado a un formato de devolución de llamada conocido.</span><span class="sxs-lookup"><span data-stu-id="9f94e-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4. <span data-ttu-id="9f94e-119">Asegúrese de que el recolector de elementos no utilizados no reclama al delegado antes de que la función de devolución de llamada complete su tarea.</span><span class="sxs-lookup"><span data-stu-id="9f94e-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="9f94e-120">Al pasar a un delegado como parámetro o pasar a un delegado contenido como campo en una estructura, se queda sin recopilar mientras dure la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f94e-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="9f94e-121">Por lo tanto, como ocurre en el siguiente ejemplo de enumeración, la función de devolución de llamada completa su tarea antes de que vuelva la llamada y no requiere que el llamador administrado realice ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="9f94e-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="9f94e-122">Sin embargo, si la función de devolución de llamada se puede invocar después de que vuelva la llamada, el llamador administrado debe seguir los pasos para asegurarse de que el delegado sigue sin recopilar hasta que finalice la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9f94e-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="9f94e-123">Para obtener información detallada sobre cómo evitar la recolección de elementos no utilizados, vea [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md) con invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="9f94e-123">For detailed information about preventing garbage collection, see [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f94e-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f94e-124">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f94e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f94e-125">See also</span></span>

- [<span data-ttu-id="9f94e-126">Funciones de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="9f94e-126">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)
- [<span data-ttu-id="9f94e-127">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="9f94e-127">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
