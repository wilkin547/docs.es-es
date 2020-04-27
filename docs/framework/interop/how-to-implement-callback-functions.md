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
ms.openlocfilehash: b7aae1e70ac736d60bed1e79291235db1c220281
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181414"
---
# <a name="how-to-implement-callback-functions"></a>Procedimiento para implementar funciones de devolución de llamada
El procedimiento y el ejemplo siguiente muestran cómo una aplicación administrada, mediante la invocación de la plataforma, puede imprimir el valor del identificador de cada ventana en el equipo local. En concreto, el uso del procedimiento y el ejemplo usan la función **EnumWindows** para recorrer la lista de ventanas y una función de devolución de llamada administrada (denominada CallBack) para imprimir el valor del identificador de ventana.  
  
### <a name="to-implement-a-callback-function"></a>Para implementar una función de devolución de llamada  
  
1. Observe la firma de la función **EnumWindows** antes de continuar con la implementación. **EnumWindows** tiene la siguiente firma:  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     Una pista para saber que esta función requiere una devolución de llamada es la presencia del argumento **lpEnumFunc**. Es habitual ver el prefijo **lp** (puntero largo) combinado con el sufijo **Func** en el nombre de los argumentos con un puntero a una función de devolución de llamada. Para consultar documentación acerca de las funciones de Win32, consulte Microsoft Platform SDK.  
  
2. Cree la función de devolución de llamada administrada. En el ejemplo, se declara un tipo de delegado, denominado `CallBack`, que toma dos argumentos (**hwnd** y **lparam**). El primer argumento es un identificador de la ventana. El segundo argumento está definido por la aplicación. En esta versión, ambos argumentos deben ser números enteros.  
  
     Generalmente, las funciones de devolución de llamada devuelven valores distintos de cero para indicar que se ha realizado correctamente y cero para indicar que se ha producido un error. En este ejemplo, el valor devuelto se establece explícitamente en **true** para continuar la enumeración.  
  
3. Cree un delegado y páselo como argumento a la función **EnumWindows**. La invocación de la plataforma convierte automáticamente el delegado a un formato de devolución de llamada conocido.  
  
4. Asegúrese de que el recolector de elementos no utilizados no reclama al delegado antes de que la función de devolución de llamada complete su tarea. Al pasar a un delegado como parámetro o pasar a un delegado contenido como campo en una estructura, se queda sin recopilar mientras dure la llamada. Por lo tanto, como ocurre en el siguiente ejemplo de enumeración, la función de devolución de llamada completa su tarea antes de que vuelva la llamada y no requiere que el llamador administrado realice ninguna acción adicional.  
  
     Sin embargo, si la función de devolución de llamada se puede invocar después de que vuelva la llamada, el llamador administrado debe seguir los pasos para asegurarse de que el delegado sigue sin recopilar hasta que finalice la función de devolución de llamada. Para obtener información detallada sobre cómo evitar la recolección de elementos no utilizados, vea [Serialización de interoperabilidad](interop-marshaling.md) con invocación de plataforma.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="see-also"></a>Vea también

- [Funciones de devolución de llamada](callback-functions.md)
- [Llamar a una función DLL](calling-a-dll-function.md)
