---
title: Comportamiento de serialización predeterminado
description: Aprenda sobre el comportamiento de serialización predeterminado en .NET. Revise la administración de memoria con serialización de interoperabilidad y consulte la serialización predeterminada para clases, delegados y tipos de valor.
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: f2a508b87d2f4a9ad92bc0f27fc44d74d8e916d3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555281"
---
# <a name="default-marshaling-behavior"></a>Comportamiento de serialización predeterminado
La serialización de interoperabilidad funciona con reglas que dictan cómo se comportan los datos asociados con parámetros de método cuando pasan entre memoria administrada y no administrada. Estas reglas integradas controlan las actividades de serialización como transformaciones de tipos de datos, si un destinatario puede cambiar los datos que recibe y devolver esos cambios al llamador, y en qué circunstancias el serializador proporciona optimizaciones de rendimiento.  
  
 En esta sección se identifican las características predeterminadas de comportamiento del servicio de serialización de interoperabilidad, y se muestra información detallada sobre la serialización de matrices, tipos booleanos, tipos de caracteres, delegados, clases, objetos, cadenas y estructuras.  
  
> [!NOTE]
> No se admite la serialización de tipos genéricos. Para más información, vea [Interoperar mediante tipos genéricos](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).  
  
## <a name="memory-management-with-the-interop-marshaler"></a>Administración de memoria con el serializador de interoperabilidad  
 El serializador de interoperabiliad siempre intenta liberar memoria asignada por código no administrado. Este comportamiento cumple con las reglas de administración de memoria COM, pero difiere de las reglas que rigen C++ nativo.  
  
 Se puede producir confusión si se prevé un comportamiento de C++ nativo (sin liberación de memoria) al usar invocación de plataforma, que automáticamente libera memoria para los punteros. Por ejemplo, la llamada al siguiente método no administrado desde una DLL de C++ no libera automáticamente memoria.  
  
### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 Sin embargo, si define el método como un prototipo de invocación de plataforma, reemplaza cada tipo **BSTR** por un tipo <xref:System.String> y llama a `MethodOne`, Common Language Runtime intenta liberar `b` dos veces. Puede cambiar el comportamiento de serialización mediante tipos <xref:System.IntPtr> en lugar de tipos **String**.  
  
 El tiempo de ejecución usa siempre el método **CoTaskMemFree** para liberar memoria. Si la memoria con la que está trabajando no se asignó con el método **CoTaskMemAlloc**, debe usar un **IntPtr** y liberar la memoria manualmente mediante el método adecuado. De forma similar, puede evitar la liberación automática de la memoria en situaciones donde nunca se debería liberar, como al usar la función **GetCommandLine** de Kernel32.dll, que devuelve un puntero a la memoria del kernel. Para obtener más información sobre cómo liberar memoria manualmente, vea el [ejemplo sobre búferes](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).  
  
## <a name="default-marshaling-for-classes"></a>Serialización predeterminada para clases  
 Las clases solo se pueden serializar con la interoperabilidad COM y siempre se serializan como interfaces. En algunos casos, la interfaz usada para calcular las referencias de la clase se conoce como interfaz de clase. Para obtener información sobre cómo reemplazar la interfaz de clase por una interfaz de su elección, consulte [Presentar la interfaz de clase](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).  
  
### <a name="passing-classes-to-com"></a>Pasar clases a COM  
 Cuando una clase administrada se pasa a COM, el serializador de interoperabilidad automáticamente encapsula la clase con un proxy COM y pasa la interfaz de clase generada por el proxy a la llamada de método COM. El proxy delega entonces todas las llamadas en la interfaz de clase al objeto administrado. El proxy también expone otras interfaces que no están implementadas explícitamente por la clase. El proxy implementa automáticamente interfaces como **IUnknown** e **IDispatch** en nombre de la clase.  
  
### <a name="passing-classes-to-net-code"></a>Pasar clases a código de .NET  
 Las coclases no suelen usarse como argumentos de método en COM. En lugar de la coclase, normalmente se pasa una interfaz predeterminada.  
  
 Cuando una interfaz se pasa a código administrado, el serializador de interoperabilidad es responsable de encapsular la interfaz en el contenedor adecuado y pasar este contenedor al método administrado. Determinar qué contenedor se usará puede resultar difícil. Cada instancia de un objeto COM tiene un solo contenedor, independientemente de cuántas interfaces implemente el objeto. Por ejemplo, un único objeto COM que implementa cinco interfaces distintas tiene un solo contenedor. El mismo contenedor expone las cinco interfaces. Si se crean dos instancias del objeto COM, también se crean dos instancias del contenedor.  
  
 Para que el contenedor mantenga el mismo tipo a lo largo del tiempo, el serializador de interoperabilidad debe identificar el contenedor correcto la primera vez que una interfaz expuesta por el objeto se pasa a través del serializador. El serializador identifica el objeto examinando una de las interfaces que implementa el objeto.  
  
 Por ejemplo, el serializador determina que el contenedor de clase se debe usar para encapsular la interfaz que se pasó a código administrado. Cuando la interfaz pasa primero por el serializador, este comprueba si la interfaz procede de un objeto conocido. Esta comprobación se produce en dos situaciones:  
  
- Se está implementando una interfaz mediante otro objeto administrado que se pasó a COM en otro lugar. El serializador puede identificar inmediatamente las interfaces expuestas por los objetos administrados y es capaz de hacer coincidir la interfaz con el objeto administrado que proporciona la implementación. El objeto administrado se pasa a continuación al método y no se necesita ningún contenedor.  
  
- Un objeto que ya se ha encapsulado se está implementando en la interfaz. Para determinar si este es el caso, el serializador consulta al objeto su interfaz **IUnknown** y compara la interfaz devuelta con las interfaces de otros objetos que ya están encapsulados. Si la interfaz es la misma que la de otro contenedor, los objetos tienen la misma identidad y el contenedor existente se pasa al método.  
  
 Si no es una interfaz de un objeto conocido, el serializador realiza lo siguiente:  
  
1. El serializador consulta al objeto la interfaz **IProvideClassInfo2**. Si se proporciona, el serializador usa el CLSID devuelto de **IProvideClassInfo2.GetGUID** para identificar la coclase que proporciona la interfaz. Con el CLSID, el serializador puede ubicar el contenedor en el Registro si previamente se ha registrado el ensamblado.  
  
2. El serializador consulta a la interfaz la interfaz **IProvideClassInfo**. Si se proporciona, el serializador usa el **ITypeInfo** devuelto desde **IProvideClassInfo.GetClassinfo** para determinar el CLSID de la clase que expone la interfaz. El serializador puede usar el CLSID para buscar los metadatos del contenedor.  
  
3. Si el serializador sigue sin poder identificar la clase, encapsula la interfaz en una clase de contenedor genérica denominada **System.__ComObject**.  
  
## <a name="default-marshaling-for-delegates"></a>Serialización predeterminada para delegados  
 Un delegado administrado se serializa como una interfaz COM o como un puntero de función según el mecanismo de llamada:  
  
- Para invocación de plataforma, se serializa un delegado como un puntero de función no administrada de forma predeterminada.  
  
- Para interoperabilidad COM, se serializa un delegado como una interfaz COM de tipo **_Delegate** de forma predeterminada. La interfaz **_Delegate** se define en la biblioteca de tipos Mscorlib.tlb y contiene el método <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>, que permite llamar al método al que hace referencia el delegado.  
  
 En la siguiente tabla se muestran las opciones de serialización para el tipo de datos de delegado administrado. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para serializar los delegados.  
  
|Tipo de enumeración|Descripción de formato no administrado|  
|----------------------|-------------------------------------|  
|**UnmanagedType.FunctionPtr**|Es un puntero de función no administrada.|  
|**UnmanagedType.Interface**|Una interfaz de tipo **_Delegate**, como se define en Mscorlib.tlb.|  
  
 Considere el siguiente código de ejemplo en el que los métodos de `DelegateTestInterface` se exportan a una biblioteca de tipos COM. Observe que solo los delegados marcados con la palabra clave **ref** (o **ByRef**) se pasan como parámetros In/Out.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);
}  
```  
  
### <a name="type-library-representation"></a>Representación de biblioteca de tipos  
  
```cpp  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 Se puede desreferenciar un puntero de función, igual que con cualquier otro puntero de función no administrada.  

En este ejemplo, al serializar los dos delegados como <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, el resultado es un elemento `int` y un puntero a un elemento `int`. Como los tipos de delegado se serializan, aquí `int` representa un puntero a un valor void (`void*`), que es la dirección del delegado en la memoria. En otras palabras, este resultado es específico para los sistemas Windows de 32 bits, ya que `int` aquí representa el tamaño del puntero de función.

> [!NOTE]
> Una referencia al puntero de función para un delegado administrado mantenido por código no administrado no impide que Common Language Runtime realice la recolección de elementos no utilizados en el objeto administrado.  
  
 Por ejemplo, el código siguiente es incorrecto porque la referencia al objeto `cb`, que se pasa al método `SetChangeHandler`, no mantiene a `cb` activo más allá de la vida del método `Test`. Una vez recopilados los elementos no utilizados del objeto `cb`, el puntero de función pasado a `SetChangeHandler` deja de ser válido.  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the
      // object from being garbage collected after the Main method
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));
   }  
}  
```  
  
 Para compensar la recolección inesperada de elementos no utilizados, el llamador debe asegurarse de que el objeto `cb` se mantiene activo mientras el puntero de función no administrada está en uso. Opcionalmente, puede hacer que el código no administrado le notifique al código administrado si el puntero de función ya no es necesario, como se muestra en el ejemplo siguiente.  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a>Serialización predeterminada para tipos de valor  
 La mayoría de los tipos de valor, como enteros y números de punto flotante, [pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) y no requieren serialización. Otros tipos que [no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) tienen representaciones distintas en memoria administrada y no administrada, y requieren serialización. Hay también otros tipos que requieren un formato explícito en el límite de interoperación.  
  
 En esta sección se proporciona información sobre los tipos de valor con el formato siguiente:  
  
- [Tipos de valor utilizados en la invocación de plataforma](#value-types-used-in-platform-invoke)  
  
- [Tipos de valor utilizados en la interoperabilidad COM](#value-types-used-in-com-interop)  
  
 Además de describir tipos con formato, en este tema se identifican [tipos de valor System](#system-value-types) que tienen un comportamiento de serialización poco habitual.  
  
 Un tipo con formato es un tipo complejo que contiene información que controla explícitamente la distribución de sus miembros en la memoria. La información de distribución de miembros se proporciona mediante el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>. La distribución puede ser uno de los siguientes valores de enumeración <xref:System.Runtime.InteropServices.LayoutKind>:  
  
- **LayoutKind.Auto**  
  
     Indica que Common Language Runtime puede volver a ordenar los miembros del tipo para lograr una mayor eficacia. Sin embargo, cuando un tipo de valor se pasa a código no administrado, la distribución de los miembros es predecible. Si se intenta serializar automáticamente una estructura de este tipo, se produce una excepción.  
  
- **LayoutKind.Sequential**  
  
     Indica que los miembros del tipo se distribuyen en la memoria no administrada en el mismo orden en que aparecen en la definición de tipo administrado.  
  
- **LayoutKind.Explicit**  
  
     Indica que los miembros se distribuyen según el <xref:System.Runtime.InteropServices.FieldOffsetAttribute> proporcionado con cada campo.  
  
### <a name="value-types-used-in-platform-invoke"></a>Tipos de valor utilizados en la invocación de plataforma  
 En el ejemplo siguiente, los tipos `Point` y `Rect` proporcionan información de distribución de miembros mediante **StructLayoutAttribute**.  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
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
```  
  
 Al serializar a código no administrado, estos tipos con formato se serializan como estructuras de estilo C. Esto proporciona una manera sencilla de llamar a una API no administrada que tiene argumentos de estructura. Por ejemplo, las estructuras `POINT` y `RECT` se pueden pasar a la función **PtInRect** de la API de Microsoft Windows del modo siguiente:  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Las estructuras se pueden pasar mediante la siguiente definición de invocación de plataforma:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "User32.dll" (
        ByRef r As Rect, p As Point) As Boolean
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("User32.dll")]
   internal static extern bool PtInRect(ref Rect r, Point p);
}
```
  
 El tipo de valor `Rect` se debe pasar por referencia porque la API no administrada espera que un puntero a un `RECT` se pase a la función. El tipo de valor `Point` se pasa por valor porque la API no administrada espera que `POINT` se pase en la pila. Esta diferencia sutil es muy importante. Las referencias se pasan a código no administrado como punteros. Los valores se pasan a código no administrado en la pila.  
  
> [!NOTE]
> Cuando un tipo con formato se serializa como una estructura, solo son accesibles los campos dentro del tipo. Si el tipo tiene métodos, propiedades o eventos, son inaccesibles desde código no administrado.  
  
 Las clases también se pueden serializar a código no administrado como estructuras de estilo C, a condición de que tengan una distribución de miembros fija. La información de distribución de miembros para una clase también se proporciona con el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>. La diferencia principal entre los tipos de valor con distribución fija y las clases con distribución fija es la forma en la que se serializan a código no administrado. Los tipos de valor se pasan por valor (en la pila) y, por consiguiente, el llamador no ve los cambios realizados por el destinatario en los miembros del tipo. Los tipos de referencia se pasan por referencia (se pasa una referencia al tipo en la pila); en consecuencia, el llamador ve todos los cambios realizados por el destinatario en miembros de un tipo que pueden transferirse en bloque de bits.  
  
> [!NOTE]
> Si un tipo de referencia tiene miembros de tipos que no pueden transferirse en bloque de bits, se requiere una conversión doble: la primera vez cuando se pasa un argumento al lado no administrado y la segunda vez en la devolución de la llamada. Debido a esta sobrecarga adicional, los parámetros In/Out deben aplicarse explícitamente a un argumento si el llamador desea ver los cambios realizados por el destinatario.  
  
 En el ejemplo siguiente, la clase `SystemTime` tiene distribución de miembros secuencial y puede pasarse a la función **GetSystemTime** de la API de Windows.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;
   public ushort wMonth;  
   public ushort wDayOfWeek;
   public ushort wDay;
   public ushort wHour;
   public ushort wMinute;
   public ushort wSecond;
   public ushort wMilliseconds;
}  
```  
  
 La función **GetSystemTime** se define como sigue:  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 La definición de invocación de plataforma equivalente para **GetSystemTime** es la siguiente:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        ByVal sysTime As SystemTime)
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("Kernel32.dll", CharSet = CharSet.Auto)]
   internal static extern void GetSystemTime(SystemTime st);
}
```
  
 Tenga en cuenta que el argumento `SystemTime` no se tipifica como argumento de referencia porque `SystemTime` es una clase, no un tipo de valor. A diferencia de los tipos de valor, las clases siempre se pasan por referencia.  
  
 En el ejemplo de código siguiente se muestra otra clase `Point` que tiene un método denominado `SetXY`. Puesto que el tipo tiene una distribución secuencial, puede pasarse a código no administrado y serializarse como una estructura. Sin embargo, el miembro `SetXY` no es invocable desde código no administrado, aunque el objeto se pase por referencia.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
### <a name="value-types-used-in-com-interop"></a>Tipos de valor utilizados en la interoperabilidad COM  
 Los tipos con formato también pueden pasarse a llamadas de métodos de interoperabilidad COM. De hecho, cuando se exportan a una biblioteca de tipos, los tipos de valor se convierten automáticamente en estructuras. Como se muestra en el ejemplo siguiente, el tipo de valor `Point` se convierte en una definición de tipo (typedef) con el nombre `Point`. Todas las referencias al tipo de valor `Point` en otro lugar de la biblioteca de tipos se reemplazan por el typedef `Point`.  
  
 **Representación de biblioteca de tipos**  
  
```cpp  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 Las mismas reglas usadas para serializar valores y referencias para llamadas de invocación de plataforma se usan al serializar a través de interfaces COM. Por ejemplo, cuando una instancia del tipo de valor `Point` se pasa de .NET Framework a COM, `Point` se pasa por valor. Si el tipo de valor `Point` se pasa por referencia, un puntero a un `Point` se pasa en la pila. El serializador de interoperabilidad no admite niveles superiores de direccionamiento indirecto (**Point** \*\*) en ninguna dirección.  
  
> [!NOTE]
> Las estructuras que tienen el valor de enumeración <xref:System.Runtime.InteropServices.LayoutKind> establecido en **Explicit** no se pueden usar en la interoperabilidad COM porque la biblioteca de tipos exportada no puede expresar una distribución explícita.  
  
### <a name="system-value-types"></a>Tipos de valor System  
 El espacio de nombres <xref:System> tiene varios tipos de valor que representan la forma de conversión boxing de los tipos primitivos en runtime. Por ejemplo, la estructura <xref:System.Int32?displayProperty=nameWithType> de tipo de valor representa la forma de conversión boxing de **ELEMENT_TYPE_I4**. En lugar de serializar estos tipos como estructuras, como otros tipos con formato, se serializan de la misma forma que los tipos primitivos a los que aplican conversión boxing. Por tanto, **System.Int32** se serializa como **ELEMENT_TYPE_I4** en lugar de como una estructura que contiene un único miembro de tipo **long**. La tabla siguiente contiene una lista de los tipos de valor en el espacio de nombres **System** que son representaciones de conversión boxing de tipos primitivos.  
  
|Tipo de valor System|Tipo de elemento|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|**ELEMENT_TYPE_BOOLEAN**|  
|<xref:System.SByte?displayProperty=nameWithType>|**ELEMENT_TYPE_I1**|  
|<xref:System.Byte?displayProperty=nameWithType>|**ELEMENT_TYPE_UI1**|  
|<xref:System.Char?displayProperty=nameWithType>|**ELEMENT_TYPE_CHAR**|  
|<xref:System.Int16?displayProperty=nameWithType>|**ELEMENT_TYPE_I2**|  
|<xref:System.UInt16?displayProperty=nameWithType>|**ELEMENT_TYPE_U2**|  
|<xref:System.Int32?displayProperty=nameWithType>|**ELEMENT_TYPE_I4**|  
|<xref:System.UInt32?displayProperty=nameWithType>|**ELEMENT_TYPE_U4**|  
|<xref:System.Int64?displayProperty=nameWithType>|**ELEMENT_TYPE_I8**|  
|<xref:System.UInt64?displayProperty=nameWithType>|**ELEMENT_TYPE_U8**|  
|<xref:System.Single?displayProperty=nameWithType>|**ELEMENT_TYPE_R4**|  
|<xref:System.Double?displayProperty=nameWithType>|**ELEMENT_TYPE_R8**|  
|<xref:System.String?displayProperty=nameWithType>|**ELEMENT_TYPE_STRING**|  
|<xref:System.IntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_I**|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_U**|  
  
 Hay algunos tipos de valor del espacio de nombres **System** que se tratan de forma diferente. Dado que el código no administrado ya tiene formatos establecidos para estos tipos, la serialización tiene reglas especiales para serializarlos. En la tabla siguiente se enumeran los tipos de valor especiales del espacio de nombres **System**, así como el tipo no administrado al que se serializan.  
  
|Tipo de valor System|Tipo IDL|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|**DATE**|  
|<xref:System.Decimal?displayProperty=nameWithType>|**DECIMAL**|  
|<xref:System.Guid?displayProperty=nameWithType>|**GUID**|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|**OLE_COLOR**|  
  
 El código siguiente muestra la definición de los tipos no administrados **DATE**, **GUID**, **DECIMAL** y **OLE_COLOR** de la biblioteca de tipos Stdole2.  
  
#### <a name="type-library-representation"></a>Representación de biblioteca de tipos  
  
```cpp  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 El código siguiente muestra las definiciones correspondientes en la interfaz `IValueTypes` administrada.  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a>Representación de biblioteca de tipos  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a>Vea también

- [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)
- [Copiar y fijar](copying-and-pinning.md)
- [Serialización predeterminada para matrices](default-marshaling-for-arrays.md)
- [Serialización predeterminada para objetos](default-marshaling-for-objects.md)
- [Serialización predeterminada para cadenas](default-marshaling-for-strings.md)
