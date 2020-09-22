---
title: Cálculo de referencias predeterminado para matrices
description: Comprenda la serialización predeterminada para matrices. Revise las matrices administradas y las matrices no administradas, pasando parámetros de matriz a código de .NET y matrices a COM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: 6bfe95576a6460efac75fd392e24acf42e36f2de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555268"
---
# <a name="default-marshaling-for-arrays"></a>Cálculo de referencias predeterminado para matrices
En una aplicación que consta únicamente de código administrado, Common Language Runtime pasa los tipos de matriz como parámetros In/Out. En cambio, el serializador de interoperabilidad pasa una matriz como parámetros In de forma predeterminada.  
  
 Con [optimización de anclaje](copying-and-pinning.md), una matriz que puede transferirse en bloque de bits puede parecer que opera como un parámetro In/Out al interactuar con objetos en el mismo contenedor. Pero si posteriormente se exporta el código a una biblioteca de tipos que se usa para generar el proxy entre equipos y esa biblioteca se usa para serializar las llamadas entre contenedores, las llamadas pueden revertir al comportamiento real del parámetro.  
  
 Las matrices son complejas por naturaleza y las distinciones entre matrices administradas y no administradas garantizan más información que otros tipos que no pueden transferirse en bloque de bits.  
  
## <a name="managed-arrays"></a>Matrices administradas  
 Los tipos de matriz administrados pueden variar, pero la clase <xref:System.Array?displayProperty=nameWithType> es la clase base de todos los tipos de matriz. La clase **System.Array** tiene propiedades para determinar el rango, la longitud y los límites inferior y superior de una matriz, así como métodos para tener acceso, ordenar, buscar, copiar y crear matrices.  
  
 Estos tipos de matriz son dinámicos y no tienen un tipo estático correspondiente definido en la biblioteca de clases base. Es conveniente pensar en cada combinación de tipo de elemento y rango como en un tipo de matriz distinto. Por tanto, una matriz unidimensional de enteros es de un tipo diferente que una matriz unidimensional de tipos dobles. De forma similar, una matriz bidimensional de enteros es diferente de una matriz unidimensional de enteros. Los límites de la matriz no se tienen en cuenta al comparar los tipos.  
  
 Como se muestra en la tabla siguiente, cualquier instancia de una matriz administrada debe ser de un tipo de elemento, rango y límite inferior específico.  
  
|Tipo de matriz administrada|Tipo de elemento|Rango|Límite inferior|Notación de firma|  
|------------------------|------------------|----------|-----------------|------------------------|  
|**ELEMENT_TYPE_ARRAY**|Especificado por el tipo.|Especificado por el rango.|Especificado opcionalmente por los límites.|*type* **[** *n*,*m* **]**|  
|**ELEMENT_TYPE_CLASS**|Desconocido|Desconocido|Desconocido|**System.Array**|  
|**ELEMENT_TYPE_SZARRAY**|Especificado por el tipo.|1|0|*type* **[** *n* **]**|  
  
## <a name="unmanaged-arrays"></a>Matrices no administradas  
 Las matrices no administradas son matrices seguras de estilo COM o matrices de estilo C de longitud fija o variable. Las matrices seguras se describen a sí mismas y contienen el tipo, rango y límites de los datos de la matriz asociada. Las matrices de estilo C son matrices con tipo unidimensionales con un límite inferior fijo de 0. El servicio de serialización proporciona compatibilidad limitada para ambos tipos de matrices.  
  
## <a name="passing-array-parameters-to-net-code"></a>Pasar parámetros de matriz a código de .NET  
 Las matrices de estilo C y las matrices seguras pueden pasarse a código de .NET desde código no administrado como una matriz segura o una matriz de estilo C. En la tabla siguiente se muestra el valor de tipo no administrado y el tipo importado.  
  
|Tipo no administrado|Tipo importado|  
|--------------------|-------------------|  
|**SafeArray(** *Type* **)**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Rango = 1, límite inferior = 0. El tamaño se conoce solo si se proporciona en la firma administrada. Las matrices seguras que no son de rango = 1 o límite inferior = 0 no se pueden serializar como **SZARRAY**.|  
|*Type*  **[]**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Rango = 1, límite inferior = 0. El tamaño se conoce solo si se proporciona en la firma administrada.|  
  
### <a name="safe-arrays"></a>Matrices seguras  
 Cuando se importa una matriz segura desde una biblioteca de tipos a un ensamblado .NET, la matriz se convierte en una matriz unidimensional de un tipo conocido (como **int**). Las mismas reglas de conversión de tipos que se aplican a los parámetros también se aplican a los elementos de la matriz. Por ejemplo, una matriz segura de tipos **BSTR** se convierte en una matriz administrada de cadenas y una matriz segura de variantes se convierte en una matriz administrada de objetos. El tipo de elemento **SAFEARRAY** se captura de la biblioteca de tipos y se guarda en el valor **SAFEARRAY** de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
 Como el rango y los límites de la matriz segura no pueden determinarse a partir de la biblioteca de tipos, el rango se considera igual a 1 y el límite inferior igual a 0. El rango y los límites se deben definir en la firma administrada generada por [TlbImp.exe (Importador de la biblioteca de tipos)](../tools/tlbimp-exe-type-library-importer.md). Si el rango pasado al método en tiempo de ejecución difiere, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>. Si difiere el tipo de la matriz pasado en tiempo de ejecución, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>. En el ejemplo siguiente se muestran las matrices seguras en código administrado y no administrado.  
  
 **Firma no administrada**  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **Firma administrada**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 Las matrices multidimensionales, o matrices seguras con límite distinto de cero, se pueden serializar en código administrado si la firma del método generada por Tlbimp.exe se modifica para indicar un tipo de elemento de **ELEMENT_TYPE_ARRAY** en lugar de **ELEMENT_ TYPE_SZARRAY**. Como alternativa, se puede usar el modificador **/sysarray** con Tlbimp.exe para importar todas las matrices como objetos <xref:System.Array?displayProperty=nameWithType>. En casos en los que se sabe que la matriz que se pasa es multidimensional, se puede editar el código de lenguaje intermedio (MSIL) de Microsoft generado mediante Tlbimp.exe y después volver a compilarlo. Para más información sobre cómo modificar código MSIL, vea [Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).  
  
### <a name="c-style-arrays"></a>Matrices de estilo C  
 Cuando se importa una matriz de estilo C desde una biblioteca de tipos a un ensamblado. NET, la matriz se convierte en **ELEMENT_TYPE_SZARRAY**.  
  
 El tipo de elemento de matriz se determina a partir de la biblioteca de tipos y se conserva durante la importación. Las mismas reglas de conversión que se aplican a los parámetros también se aplican a los elementos de la matriz. Por ejemplo, una matriz de tipos **LPStr** se convierte en una matriz de tipos **String**. Tlbimp.exe captura el tipo de elemento de matriz y aplica el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro.  
  
 El rango de matriz se considera igual a 1. Si el rango es mayor que 1, la matriz se serializa como una matriz unidimensional en el orden de importancia de la columna. El límite inferior es siempre igual a 0.  
  
 Las bibliotecas de tipos pueden contener matrices de longitud fija o variable. Tlbimp.exe solo puede importar matrices de longitud fija desde bibliotecas de tipos porque las bibliotecas de tipos no tienen la información necesaria para serializar matrices de longitud variable. Con las matrices de longitud fija, el tamaño se importa desde la biblioteca de tipos y se captura en el atributo **MarshalAsAttribute** que se aplica al parámetro.  
  
 Debe definir manualmente las bibliotecas de tipos que contienen matrices de longitud variable, como se muestra en el ejemplo siguiente.  
  
 **Firma no administrada**  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **Firma administrada**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 Aunque puede aplicar los atributos **size_is** o **length_is** a una matriz en código fuente de lenguaje de definición de interfaz (IDL) para transmitir el tamaño a un cliente, el compilador del Lenguaje de definición de interfaz de Microsoft (MIDL) no transmite esa información a la biblioteca de tipos. Sin conocer el tamaño, el servicio de serialización de interoperabilidad no puede serializar los elementos de matriz. Por tanto, las matrices de longitud variable se importan como argumentos por referencia. Por ejemplo:  
  
 **Firma no administrada**  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **Firma administrada**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 Puede proporcionar al serializador el tamaño de la matriz si modifica el código de lenguaje intermedio de Microsoft (MSIL) generado mediante Tlbimp.exe y después lo vuelve a compilar. Para más información sobre cómo modificar código MSIL, vea [Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)). Para indicar el número de elementos de la matriz, aplique el tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro de matriz de la definición de método administrado de una de las maneras siguientes:  
  
- Identifique otro parámetro que contenga el número de elementos de la matriz. Los parámetros se identifican por posición, empezando con el primer parámetro como el número 0.
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- Defina el tamaño de la matriz como una constante. Por ejemplo:  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 Al serializar matrices desde código no administrado a código administrado, el serializador comprueba el atributo **MarshalAsAttribute** asociado con el parámetro para determinar el tamaño de la matriz. Si no se especifica el tamaño de la matriz, solo se serializa un elemento.  
  
> [!NOTE]
> El atributo **MarshalAsAttribute** no tiene ningún efecto sobre la serialización de matrices administradas en código no administrado. En esa dirección, el tamaño de la matriz se determina mediante examen. No hay ninguna manera de serializar un subconjunto de una matriz administrada.  
  
 El serializador de interoperabilidad usa los métodos **CoTaskMemAlloc** y **CoTaskMemFree** para asignar y recuperar memoria. La asignación de memoria realizada por el código no administrado también debe usar estos métodos.  
  
## <a name="passing-arrays-to-com"></a>Pasar matrices a COM  
 Todos los tipos de matriz administrados pueden pasarse a código no administrado desde código administrado. Según el tipo administrado y los atributos que se le apliquen, se puede obtener acceso a la matriz como una matriz segura o una matriz de estilo C, como se muestra en la tabla siguiente.  
  
|Tipo de matriz administrada|Exportado como|  
|------------------------|-----------------|  
|**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> El tipo se proporciona en la firma. El rango siempre es 1, el límite inferior es siempre 0. El tamaño siempre se conoce en tiempo de ejecución.|  
|**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]|**UnmanagedType.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> El tipo, el rango y los límites se proporcionan en la firma. El tamaño siempre se conoce en tiempo de ejecución.|  
|**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>** >**|**UT_Interface**<br /><br /> **UnmanagedType.SafeArray(** *type* **)**<br /><br /> El tipo, el rango, los límites y el tamaño siempre se conocen en tiempo de ejecución.|  
  
 Hay una limitación en la automatización OLE relacionada con las matrices de estructuras que contienen LPSTR o LPWSTR.  Por tanto, los campos **String** tienen que serializarse como **UnmanagedType.BSTR**. De lo contrario, se producirá una excepción.  
  
### <a name="element_type_szarray"></a>ELEMENT_TYPE_SZARRAY  
 Cuando un método que contiene un parámetro **ELEMENT_TYPE_SZARRAY** (matriz unidimensional) se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una **SAFEARRAY** de un tipo determinado. Las mismas reglas de conversión se aplican a los tipos de elemento de matriz. El contenido de la matriz administrada se copia automáticamente de la memoria administrada a **SAFEARRAY**. Por ejemplo:  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 El rango de las matrices seguras siempre es 1 y el límite inferior siempre es 0. El tamaño se determina en tiempo de ejecución por el tamaño de la matriz administrada que se pasa.  
  
 La matriz también se puede serializar como una matriz de estilo C mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Por ejemplo:  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Aunque el serializador no tiene la información de longitud necesaria para serializar la matriz, la longitud de la matriz normalmente se pasa como argumento independiente para transmitir la longitud al destinatario de la llamada.  
  
### <a name="element_type_array"></a>ELEMENT_TYPE_ARRAY  
 Cuando un método que contiene un parámetro **ELEMENT_TYPE_ARRAY** se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una **SAFEARRAY** de un tipo determinado. El contenido de la matriz administrada se copia automáticamente de la memoria administrada a **SAFEARRAY**. Por ejemplo:  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 El rango, el tamaño y los límites de las matrices seguras se determinan en tiempo de ejecución mediante las características de la matriz administrada.  
  
 La matriz también se puede serializar como una matriz de estilo C aplicando el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Por ejemplo:  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Las matrices anidadas no se pueden serializar. Por ejemplo, la siguiente firma genera un error cuando se exporta con el [exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a>ELEMENT_TYPE_CLASS \<System.Array>  
 Cuando un método que contiene un parámetro <xref:System.Array?displayProperty=nameWithType> se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una interfaz **_Array**. El contenido de la matriz administrada es accesible a través de los métodos y propiedades de la interfaz **_Array**. **System.Array** también se puede serializar como una **SAFEARRAY** mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Cuando se serializa como una matriz segura, los elementos de matriz se calculan como variantes. Por ejemplo:  
  
#### <a name="managed-signature"></a>Firma administrada  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a>Prototipo no administrado  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a>Matrices en estructuras  
 Las estructuras no administradas pueden contener matrices insertadas. De forma predeterminada, estos campos de matriz insertados se calculan como SAFEARRAY. En el ejemplo siguiente, `s1` es una matriz insertada que se asigna directamente desde la propia estructura.  
  
#### <a name="unmanaged-representation"></a>Representación no administrada  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Las matrices se pueden serializar como <xref:System.Runtime.InteropServices.UnmanagedType>, lo que requiere que establezca el campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. El tamaño solo se puede establecer como una constante. En el código siguiente se muestra la definición administrada correspondiente de `MyStruct`.  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Comportamiento predeterminado del cálculo de referencias](default-marshaling-behavior.md)
- [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)
- [Atributos direccionales](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Copiar y fijar](copying-and-pinning.md)
