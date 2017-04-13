---
title: "Default Marshaling for Arrays | Microsoft Docs"
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
  - "interop marshaling, arrays"
  - "arrays, interop marshaling"
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Default Marshaling for Arrays
En una aplicación que consta totalmente de código administrado, Common Language Runtime pasa los tipos de matriz como parámetros In\/Out.  Por el contrario, el contador de referencias interoperativo pasa una matriz como parámetros In de forma predeterminada.  
  
 Con la [optimización de anclaje](../../../docs/framework/interop/copying-and-pinning.md), una matriz que puede transferirse en bloque de bits puede parecer que opera como un parámetro In\/Out al interactuar con objetos del mismo apartamento.  No obstante, si después exporta el código a una biblioteca de tipos utilizada para generar el proxy entre equipos y esa biblioteca se usa para calcular las referencias de las llamadas entre apartamentos, las llamadas pueden volver a un comportamiento real del parámetro como In.  
  
 Las matrices son complejas por naturaleza y las distinciones entre matrices administradas y no administradas garantizan más información que otros tipos que no pueden transferirse en bloque de bits.  En este tema se ofrece la siguiente información sobre el cálculo de referencias de matrices:  
  
-   [Matrices administradas](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [Matrices no administradas](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [Pasar parámetros de matriz a código de .NET](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [Pasar matrices a COM](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## Matrices administradas  
 Los tipos de matrices administradas pueden variar; sin embargo, <xref:System.Array?displayProperty=fullName> es la clase base de todos los tipos de matrices.  La clase **System.Array** tiene propiedades para determinar el rango, la longitud y los límites inferior y superior de una matriz, así como métodos para tener acceso, ordenar, buscar, copiar y crear matrices.  
  
 Estos tipos de matriz son dinámicos y no tienen un tipo estático correspondiente definido en la biblioteca de clases base.  Resulta conveniente pensar en cada combinación de rango y tipo de elementos como un tipo distinto de matriz.  Por lo tanto, una matriz unidimensional de tipos integer es distinta de una matriz unidimensional de tipos double.  Igualmente, una matriz bidimensional de datos de tipo integer es diferente de una matriz unidimensional de datos de tipo integer.  Los límites de la matriz no se consideran al comparar los tipos.  
  
 Como se muestra en la tabla siguiente, cualquier instancia de una matriz administrada debe ser de un tipo de elemento, rango y límite inferior específicos.  
  
|Tipo de matriz administrada|Tipo de elemento|Rango|Límite inferior|Notación de firma|  
|---------------------------------|----------------------|-----------|---------------------|-----------------------|  
|**ELEMENT\_TYPE\_ARRAY**|Especificado por tipo.|Especificado por rango.|Especificado opcionalmente mediante límites.|*tipo* **\[** *n*,*m* **\]**|  
|**ELEMENT\_TYPE\_CLASS**|Desconocido|Desconocido|Desconocido|**System.Array**|  
|**ELEMENT\_TYPE\_SZARRAY**|Especificado por tipo.|1|0|*tipo* **\[** *n* **\]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## Matrices no administradas  
 Las matrices no administradas son matrices seguras del estilo de COM o matrices del estilo de C con longitud fija o variable.  Las matrices seguras son matrices que se describen a sí mismas y que contienen el tipo, rango y límites de los datos de la matriz asociada.  Las matrices del estilo de C son matrices con tipo unidimensionales con un límite inferior fijo de 0.  El servicio de cálculo de referencias tiene compatibilidad limitada con ambos tipos de matrices.  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## Pasar parámetros de matriz a código de .NET  
 Las matrices del estilo de C y las matrices seguras pueden pasarse a código de .NET desde código no administrado como una matriz segura o como una matriz del estilo de C.  En la tabla siguiente se muestra el valor del tipo no administrado y el tipo importado.  
  
|Tipo no administrado|Tipo importado|  
|--------------------------|--------------------|  
|**SafeArray\(** *Tipo* **\)**|**ELEMENT\_TYPE\_SZARRAY** **\<** *tipoConvertido* **\>**<br /><br /> Rango \= 1, límite inferior \= 0.  Solo se conoce el tamaño si se proporciona en la firma administrada.  En las matrices seguras que no son de rango \= 1 o límite inferior \= 0 no pueden calcularse las referencias como **SZARRAY**.|  
|*Tipo*  **\[\]**|**ELEMENT\_TYPE\_SZARRAY** **\<** *tipoConvertido* **\>**<br /><br /> Rango \= 1, límite inferior \= 0.  Solo se conoce el tamaño si se proporciona en la firma administrada.|  
  
### Matrices seguras  
 Cuando se importa una matriz segura de una biblioteca de tipos a un ensamblado de .NET, la matriz se convierte en una matriz unidimensional de un tipo conocido \(como **int**\).  Las mismas reglas de conversión que se aplican a parámetros también se aplican a los elementos de una matriz.  Por ejemplo, una matriz segura de tipos **BSTR** se convierte en una matriz administrada de cadenas y una matriz segura de variantes se convierte en una matriz administrada de objetos.  El tipo de elemento **SAFEARRAY** se captura de la biblioteca de tipos y se guarda en el valor **SAFEARRAY** de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
 Puesto que el rango y los límites de la matriz segura no pueden determinarse a partir de la biblioteca de tipos, el rango se considera igual a 1 y el límite inferior igual a 0.  El rango y los límites se deben definir en la firma administrada generada por el [Importador de la biblioteca de tipos \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  Si el rango pasado al método en tiempo de ejecución difiere, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.  Si difiere el tipo de la matriz pasado en tiempo de ejecución, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.  En el ejemplo siguiente se muestran matrices seguras en código administrado y no administrado.  
  
 **Prototipo no administrado**  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **Prototipo administrado**  
  
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
  
 En las matrices seguras multidimensionales o que no tienen como límite el cero se pueden calcular las referencias en código administrado si la firma de método que produce la herramienta Tlbimp.exe se modifica para indicar un tipo de elemento de **ELEMENT\_TYPE\_ARRAY** en lugar de **ELEMENT\_TYPE\_SZARRAY**.  También puede utilizar el modificador **\/sysarray** con Tlbimp.exe para importar todas las matrices como objetos <xref:System.Array?displayProperty=fullName>.  En los casos en los que se sabe que la matriz pasada es multidimensional, puede modificar el código MSIL \(Microsoft Intermediate Language, Lenguaje intermedio de Microsoft\) que produce Tlbimp.exe y después volver a compilarlo.  Para obtener detalles sobre cómo modificar código MSIL, vea [Personalizar contenedores invocables en tiempo de ejecución](http://msdn.microsoft.com/es-es/4652beaf-77d0-4f37-9687-ca193288c0be).  
  
### Matrices al estilo de C  
 Cuando se importa una matriz al estilo de C de una biblioteca de tipos a un ensamblado de .NET, se convierte a **ELEMENT\_TYPE\_SZARRAY**.  
  
 El tipo de elemento de matriz se determina a partir de la biblioteca de tipos y se conserva durante la importación.  Las mismas reglas de conversión aplicadas a los parámetros también se aplican a los elementos de una matriz.  Por ejemplo, una matriz de tipos **LPStr** se convierte en una matriz de tipos **String**.  La herramienta Tlbimp.exe captura el tipo de elemento de matriz y aplica el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro.  
  
 Se supone que el rango de la matriz es igual a 1.  Si el rango es mayor que 1, las referencias de la matriz se calculan como si se tratara de una matriz unidimensional en el orden de la columna principal.  El límite inferior siempre equivale a 0.  
  
 Las bibliotecas de tipos pueden contener matrices de longitud fija o variable.  El programa Tlbimp.exe sólo puede importar matrices de longitud fija desde bibliotecas de tipos porque éstas carecen de la información necesaria para calcular las referencias de matrices de longitud variable.  Con las matrices de longitud fija, el tamaño se importa desde la biblioteca de tipos y se captura en el atributo **MarshalAsAttribute** aplicado al parámetro.  
  
 Debe definir manualmente las bibliotecas de tipos que contienen matrices de longitud variable, como se muestra en el ejemplo siguiente.  
  
 **Prototipo no administrado**  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **Prototipo administrado**  
  
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
  
 Aunque puede aplicar los atributos **size\_is** o **length\_is** a una matriz en el origen IDL \(Interface Definition Language, Lenguaje de definición de interfaz\) para transmitir el tamaño a un cliente, el compilador de MIDL \(Microsoft Interface Definition Language, Lenguaje de definición de interfaz de Microsoft\) no propaga esa información a la biblioteca de tipos.  Sin conocer el tamaño, el servicio de cálculo de referencia de interoperabilidad no puede calcular las referencias de los elementos de la matriz.  Como consecuencia, las matrices de longitud variable se importan como argumentos por referencia.  Por ejemplo:  
  
 **Prototipo no administrado**  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **Prototipo administrado**  
  
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
  
 Puede proporcionar el tamaño de la matriz al contador de referencias si modifica el código de MSIL generado por la herramienta Tlbimp.exe y después lo vuelve a compilar.  Para obtener detalles sobre cómo modificar código MSIL, vea [Personalizar contenedores invocables en tiempo de ejecución](http://msdn.microsoft.com/es-es/4652beaf-77d0-4f37-9687-ca193288c0be).  Para indicar el número de elementos de la matriz, aplique el tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro de matriz de la definición de método administrado de uno de estos modos:  
  
-   Mediante la identificación de otro parámetro que contenga el número de elementos de la matriz.  Los parámetros se identifican por posición, empezando con el primer parámetro como el número 0.  \[Visual Basic\]  
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       <MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   Define el tamaño de la matriz como una constante.  Por ejemplo:  
  
    ```vb  
    Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 Al calcular las referencias de matrices de código no administrado a código administrado, el contador de referencias comprueba el atributo **MarshalAsAttribute** asociado con el parámetro para determinar el tamaño de la matriz.  Si no se especifica dicho tamaño, sólo se calcularán las referencias de un elemento.  
  
> [!NOTE]
>  El atributo **MarshalAsAttribute** no tiene efecto al calcular las referencias de matrices administradas para código no administrado.  En esa dirección, el tamaño de la matriz se determina mediante examen.  No es posible calcular las referencias de un subconjunto de una matriz administrada.  
  
 El contador de referencias interoperativo utiliza los métodos **CoTaskMemAlloc** y **CoTaskMemFree** para asignar y recuperar memoria.  En la asignación de memoria que realiza el código no administrado también se deben emplear estos métodos.  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## Pasar matrices a COM  
 Todos los tipos de matrices administradas pueden pasarse a código no administrado desde código administrado.  En función del tipo administrado y de los atributos que se le aplican, se puede tener acceso a la matriz como una matriz segura o como una matriz al estilo de C, como se muestra en la tabla siguiente.  
  
|Tipo de matriz administrada|Se exporta como|  
|---------------------------------|---------------------|  
|**ELEMENT\_TYPE\_SZARRAY** **\<** *tipo* **\>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray\(** *tipo* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Tipo proporcionado en la firma.  El rango siempre es 1, el límite inferior siempre es 0.  El tamaño siempre se conoce en tiempo de ejecución.|  
|**ELEMENT\_TYPE\_ARRAY** **\<** *tipo* **\>** **\<** *rango* **\>**\[**\<** *límites* **\>**\]|**UnmanagedType.SafeArray\(** *tipo* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> El tipo, rango y límites se proporcionan en la firma.  El tamaño siempre se conoce en tiempo de ejecución.|  
|**ELEMENT\_TYPE\_CLASS** **\<** <xref:System.Array?displayProperty=fullName> **\>**|**UT\_Interface**<br /><br /> **UnmanagedType.SafeArray\(** *tipo* **\)**<br /><br /> El tipo, rango, límites y tamaño siempre se conocen en tiempo de ejecución.|  
  
 Hay una limitación en la automatización OLE relacionada con las matrices de estructuras que contienen LPSTR o LPWSTR.  Por consiguiente, las referencias de los campos **String** se tienen que calcular como referencias **UnmanagedType.BSTR**.  De lo contrario, se producirá una excepción.  
  
### ELEMENT\_TYPE\_SZARRAY  
 Cuando un método que contiene un parámetro **ELEMENT\_TYPE\_SZARRAY** \(matriz unidimensional\) se exporta de un ensamblado de .NET a una biblioteca de tipos, el parámetro de la matriz se convierte a una matriz **SAFEARRAY** de un tipo determinado.  Las mismas reglas de conversión se aplican a los tipos de los elementos de una matriz.  El contenido de la matriz administrada se copia automáticamente de la memoria administrada a la matriz **SAFEARRAY**.  Por ejemplo:  
  
#### Prototipo administrado  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### Prototipo no administrado  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 El rango de las matrices seguras siempre es 1 y el límite inferior siempre es 0.  El tamaño se determina en tiempo de ejecución por el tamaño de la matriz administrada que se está pasando.  
  
 En la matriz también se pueden calcular las referencias como una matriz del estilo de C con el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  Por ejemplo:  
  
#### Prototipo administrado  
  
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
  
#### Prototipo no administrado  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 Aunque el contador de referencias dispone de la información de longitud necesaria para calcular las referencias de la matriz, la longitud de ésta normalmente se pasa como argumento aparte para transmitir la longitud al destinatario de la llamada.  
  
### ELEMENT\_TYPE\_ARRAY  
 Cuando un método que contiene un parámetro **ELEMENT\_TYPE\_ARRAY** se exporta de un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte a una matriz **SAFEARRAY** de un tipo determinado.  El contenido de la matriz administrada se copia automáticamente de la memoria administrada a la matriz **SAFEARRAY**.  Por ejemplo:  
  
#### Prototipo administrado  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### Prototipo no administrado  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 El rango, tamaño y límites de las matrices seguras se determinan en tiempo de ejecución mediante las características de la matriz administrada.  
  
 En la matriz también se pueden calcular las referencias como una matriz del estilo de C aplicando el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  Por ejemplo:  
  
#### Prototipo administrado  
  
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
  
#### Prototipo no administrado  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 No se pueden calcular las referencias de matrices anidadas.  Por ejemplo, la siguiente firma genera un error cuando se exporta con la herramienta [Exportador de la biblioteca de tipos \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).  
  
#### Prototipo administrado  
  
```vb  
Sub [New](ar()()() As Long)  
  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### ELEMENT\_TYPE\_CLASS \<System.Array\>  
 Cuando un método que contiene un parámetro <xref:System.Array?displayProperty=fullName> se exporta de un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte a una interfaz **\_Array**.  Sólo se puede tener acceso al contenido de la matriz administrada mediante los métodos y propiedades de la interfaz **\_Array**.  También se pueden calcular las referencias de **System.Array** como una matriz **SAFEARRAY** mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  Cuando se calculan las referencias como una matriz segura, en los elementos de la matriz las referencias se calculan como variantes.  Por ejemplo:  
  
#### Prototipo administrado  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### Prototipo no administrado  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### Matrices en estructuras  
 Las estructuras no administradas pueden contener matrices incrustadas.  De forma predeterminada, las referencias de estos campos de matrices incrustadas se calculan como un SAFEARRAY.  En el ejemplo siguiente, `s1` es una matriz incrustada que se asigna directamente dentro de la propia estructura.  
  
#### Representación no administrada  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Se pueden calcular las referencias de las matrices como [UnmanagedType.ByValArray](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic), lo que requiere que establezca el campo [MarshalAsAttribute.SizeConst](frlrfSystemRuntimeInteropServicesMarshalAsAttributeClassTopic).  El tamaño sólo se puede establecer como una constante.  En el código siguiente se muestra la definición administrada correspondiente de  `MyStruct`.  
  
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
  
## Vea también  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/es-es/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md)