---
title: "Default Marshaling for Objects | Microsoft Docs"
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
  - "objects, interop marshaling"
  - "interop marshaling, objects"
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Default Marshaling for Objects
Los parámetros y campos cuyo tipo es <xref:System.Object?displayProperty=fullName> pueden exponerse a código no administrado como uno de los tipos siguientes:  
  
-   Una variante cuando el objeto es un parámetro.  
  
-   Una interfaz cuando el objeto es un campo de una estructura.  
  
 Sólo la interoperatividad COM admite el cálculo de referencias para tipos de objetos.  De forma predeterminada, se calcularán las referencias de objetos para variantes COM.  Estas reglas sólo se aplican al tipo **Object** y no son válidas para objetos fuertemente tipados que se derivan de la clase **Object**.  
  
 Este tema ofrece la siguiente información adicional sobre el cálculo de referencias de tipos de objetos:  
  
-   [Cálculo de referencias de opciones](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [Cálculo de referencias de objetos para interfaces](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [Cálculo de referencias de objetos para variantes](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [Cálculo de referencias de variantes para objetos](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [Cálculo de referencias de variantes ByRef](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## Cálculo de referencias de opciones  
 En la tabla siguiente se muestran las opciones de cálculo de referencias para el tipo de datos **Object**.  El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular las referencias de objetos.  
  
|Tipo de enumeración|Descripción de formato no administrado|  
|-------------------------|--------------------------------------------|  
|**UnmanagedType.Struct**<br /><br /> \(valor predeterminado para los parámetros\)|Variante del estilo de COM.|  
|**UnmanagedType.Interface**|Interfaz **IDispatch**, si es posible; si no, interfaz **IUnknown**.|  
|**UnmanagedType.IUnknown**<br /><br /> \(valor predeterminado para los campos\)|Interfaz **IUnknown**.|  
|**UnmanagedType.IDispatch**|Una interfaz **IDispatch**.|  
  
 En el ejemplo siguiente se muestra la definición de interfaz administrada para `MarshalObject`.  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 En el código siguiente se exporta la interfaz `MarshalObject` a una biblioteca de tipos.  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
>  El contador de referencias de interoperabilidad libera automáticamente cualquier objeto asignado dentro de la variante tras la llamada.  
  
 En el ejemplo siguiente se muestra un tipo de valor con formato.  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 En el código siguiente se exporta el tipo con formato a una biblioteca de tipos.  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## Cálculo de referencias de objetos para interfaces  
 Cuando un objeto se expone en COM como una interfaz, ésta es la interfaz de clase para el tipo administrado <xref:System.Object> \(la interfaz **\_Object**\).  Esta interfaz tiene el tipo**IDispatch** \([UnmanagedType.IDispatch](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic)\) o **IUnknown** \(**UnmanagedType.IUnknown**\) en la biblioteca de tipos resultante.  Los clientes COM pueden invocar dinámicamente a los miembros de la clase administrada o a cualquier miembro implementado mediante sus clases derivadas a través de la interfaz **\_Object**.  Asimismo, el cliente puede llamar a **QueryInterface** para obtener cualquier otra interfaz que implemente explícitamente el tipo administrado.  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## Cálculo de referencias de objetos para variantes  
 Cuando se calculan las referencias de un objeto para una variante, el tipo de variante interna se determina en tiempo de ejecución, en función de las reglas siguientes:  
  
-   Si la referencia de objeto es null \(**Nothing** en Visual Basic\), se calculan las referencias del objeto para una variante de tipo **VT\_EMPTY**.  
  
-   Si el objeto es una instancia de cualquier tipo que aparezca en la tabla siguiente, el tipo de variante resultante se determina mediante las reglas integradas en el contador de referencias, enumeradas en la tabla.  
  
-   Otros objetos que necesitan controlar explícitamente el comportamiento del cálculo de referencias pueden implementar la interfaz <xref:System.IConvertible>.  En ese caso, el tipo de variante se determina mediante el tipo de código que devuelve el método <xref:System.IConvertible.GetTypeCode%2A?displayProperty=fullName>.  De lo contrario, se calcularán las referencias del objeto como variante de tipo **VT\_UNKNOWN**.  
  
### Cálculo de referencias de tipos de sistema para variantes  
 En la tabla siguiente se muestran tipos de objeto administrado y sus tipos de variante COM correspondientes.  Estos tipos sólo se convierten cuando la firma del método que se llama es de tipo <xref:System.Object?displayProperty=fullName>.  
  
|Tipo de objeto|Tipo de variante COM|  
|--------------------|--------------------------|  
|Referencia de objeto null \(**Nothing** en Visual Basic\).|**VT\_EMPTY**|  
|<xref:System.DBNull?displayProperty=fullName>|**VT\_NULL**|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=fullName>|**VT\_ERROR**|  
|<xref:System.Reflection.Missing?displayProperty=fullName>|**VT\_ERROR** con **E\_PARAMNOTFOUND**|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=fullName>|**VT\_DISPATCH**|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=fullName>|**VT\_UNKNOWN**|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=fullName>|**VT\_CY**|  
|<xref:System.Boolean?displayProperty=fullName>|**VT\_BOOL**|  
|<xref:System.SByte?displayProperty=fullName>|**VT\_I1**|  
|<xref:System.Byte?displayProperty=fullName>|**VT\_UI1**|  
|<xref:System.Int16?displayProperty=fullName>|**VT\_I2**|  
|<xref:System.UInt16?displayProperty=fullName>|**VT\_UI2**|  
|<xref:System.Int32?displayProperty=fullName>|**VT\_I4**|  
|<xref:System.UInt32?displayProperty=fullName>|**VT\_UI4**|  
|<xref:System.Int64?displayProperty=fullName>|**VT\_I8**|  
|<xref:System.UInt64?displayProperty=fullName>|**VT\_UI8**|  
|<xref:System.Single?displayProperty=fullName>|**VT\_R4**|  
|<xref:System.Double?displayProperty=fullName>|**VT\_R8**|  
|<xref:System.Decimal?displayProperty=fullName>|**VT\_DECIMAL**|  
|<xref:System.DateTime?displayProperty=fullName>|**VT\_DATE**|  
|<xref:System.String?displayProperty=fullName>|**VT\_BSTR**|  
|<xref:System.IntPtr?displayProperty=fullName>|**VT\_INT**|  
|<xref:System.UIntPtr?displayProperty=fullName>|**VT\_UINT**|  
|<xref:System.Array?displayProperty=fullName>|**VT\_ARRAY**|  
  
 Utilizando la interfaz `MarshalObject` definida en el ejemplo anterior, en el ejemplo de código siguiente se muestra cómo pasar varios tipos de variantes a un servidor COM.  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 En los tipos COM que no tienen tipos administrados correspondientes se pueden calcular las referencias usando clases contenedoras como <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> y <xref:System.Runtime.InteropServices.CurrencyWrapper>.  En el ejemplo de código siguiente se muestra cómo utilizar estos contenedores para pasar varios tipos de variantes a un servidor COM.  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 Las clases contenedoras se definen en el espacio de nombres <xref:System.Runtime.InteropServices>.  
  
### Cálculo de referencias de la interfaz IConvertible para variantes  
 Los tipos que no aparecían en la sección anterior pueden controlar cómo se calculan sus referencias mediante la implementación de la interfaz <xref:System.IConvertible>.  Si el objeto implementa la interfaz **IConvertible**, el tipo de variante COM se determina en tiempo de ejecución mediante el valor de la enumeración <xref:System.TypeCode> que devuelve el método <xref:System.IConvertible.GetTypeCode%2A?displayProperty=fullName>.  
  
 En la tabla siguiente se muestran los posibles valores para la enumeración **TypeCode** y el tipo de variante COM correspondiente para cada valor.  
  
|TypeCode|Tipo de variante COM|  
|--------------|--------------------------|  
|**TypeCode.Empty**|**VT\_EMPTY**|  
|**TypeCode.Object**|**VT\_UNKNOWN**|  
|**TypeCode.DBNull**|**VT\_NULL**|  
|**TypeCode.Boolean**|**VT\_BOOL**|  
|**TypeCode.Char**|**VT\_UI2**|  
|**TypeCode.Sbyte**|**VT\_I1**|  
|**TypeCode.Byte**|**VT\_UI1**|  
|**TypeCode.Int16**|**VT\_I2**|  
|**TypeCode.UInt16**|**VT\_UI2**|  
|**TypeCode.Int32**|**VT\_I4**|  
|**TypeCode.UInt32**|**VT\_UI4**|  
|**TypeCode.Int64**|**VT\_I8**|  
|**TypeCode.UInt64**|**VT\_UI8**|  
|**TypeCode.Single**|**VT\_R4**|  
|**TypeCode.Double**|**VT\_R8**|  
|**TypeCode.Decimal**|**VT\_DECIMAL**|  
|**TypeCode.DateTime**|**VT\_DATE**|  
|**TypeCode.String**|**VT\_BSTR**|  
|No se admite.|**VT\_INT**|  
|No se admite.|**VT\_UINT**|  
|No se admite.|**VT\_ARRAY**|  
|No se admite.|**VT\_RECORD**|  
|No se admite.|**VT\_CY**|  
|No se admite.|**VT\_VARIANT**|  
  
 El valor de la variante COM se determina llamando a la interfaz **IConvertible.To** *Type*, donde **To** *Type* es la rutina de conversión que corresponde al tipo devuelto por **IConvertible.GetTypeCode**.  Por ejemplo, las referencias de un objeto que devuelve **TypeCode.Double** de **IConvertible.GetTypeCode** se calculan como una variante COM de tipo **VT\_R8**.  Puede obtener el valor de la variante \(almacenado en el campo **dblVal** de la variante COM\) si lo convierte a la interfaz **IConvertible** y llama al método <xref:System.IConvertible.ToDouble%2A>.  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## Cálculo de referencias de variantes para objetos  
 Al calcular las referencias de una variante para un objeto, el tipo y, en ocasiones, el valor de la variante cuyas referencias se calculan determinan el tipo de objeto producido.  En la tabla siguiente se identifica cada tipo de variante y el tipo de objeto correspondiente que crea el contador de referencias cuando se pasa una variante COM a .NET Framework.  
  
|Tipo de variante COM|Tipo de objeto|  
|--------------------------|--------------------|  
|**VT\_EMPTY**|Referencia de objeto null \(**Nothing** en Visual Basic\).|  
|**VT\_NULL**|<xref:System.DBNull?displayProperty=fullName>|  
|**VT\_DISPATCH**|**System.\_\_ComObject** o null si \(pdispVal \=\= null\)|  
|**VT\_UNKNOWN**|**System.\_\_ComObject** o null si \(pdispVal \=\= null\)|  
|**VT\_ERROR**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_BOOL**|<xref:System.Boolean?displayProperty=fullName>|  
|**VT\_I1**|<xref:System.SByte?displayProperty=fullName>|  
|**VT\_UI1**|<xref:System.Byte?displayProperty=fullName>|  
|**VT\_I2**|<xref:System.Int16?displayProperty=fullName>|  
|**VT\_UI2**|<xref:System.UInt16?displayProperty=fullName>|  
|**VT\_I4**|<xref:System.Int32?displayProperty=fullName>|  
|**VT\_UI4**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_I8**|<xref:System.Int64?displayProperty=fullName>|  
|**VT\_UI8**|<xref:System.UInt64?displayProperty=fullName>|  
|**VT\_R4**|<xref:System.Single?displayProperty=fullName>|  
|**VT\_R8**|<xref:System.Double?displayProperty=fullName>|  
|**VT\_DECIMAL**|<xref:System.Decimal?displayProperty=fullName>|  
|**VT\_DATE**|<xref:System.DateTime?displayProperty=fullName>|  
|**VT\_BSTR**|<xref:System.String?displayProperty=fullName>|  
|**VT\_INT**|<xref:System.Int32?displayProperty=fullName>|  
|**VT\_UINT**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_ARRAY** &#124; **VT\_\***|<xref:System.Array?displayProperty=fullName>|  
|**VT\_CY**|<xref:System.Decimal?displayProperty=fullName>|  
|**VT\_RECORD**|Tipo de valor correspondiente al que se le ha aplicado la conversión boxing.|  
|**VT\_VARIANT**|No se admite.|  
  
 Es posible que los tipos de variante que se pasan de COM a código administrado y de nuevo a COM no se mantengan sin cambios durante toda la llamada.  Considere lo que sucede cuando una variante de tipo **VT\_DISPATCH** se pasa de COM a .NET Framework.  Durante el cálculo de referencias, la variante se convierte a <xref:System.Object?displayProperty=fullName>.  Si **Object** se pasa de nuevo a COM, se calculan de nuevo sus referencias para una variante de tipo **VT\_UNKNOWN**.  No hay ninguna garantía de que la variante producida cuando se calculan las referencias de un objeto a partir de código administrado para COM sea del mismo tipo que la variante utilizada inicialmente para producir el objeto.  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## Cálculo de referencias de variantes ByRef  
 Aunque las variantes se pueden pasar por valor o por referencia, el marcador **VT\_BYREF** también se puede utilizar con cualquier tipo de variante para indicar que su contenido se está pasando por referencia en vez de por valor.  La diferencia entre el cálculo de referencias de variantes por referencia y con la marca **VT\_BYREF** establecida puede resultar confuso.  En la ilustración siguiente se aclaran las diferencias.  
  
 ![Variant pasado a la pila](../../../docs/framework/interop/media/interopvariant.gif "interopvariant")  
Variantes pasadas por valor y por referencia  
  
 **Comportamiento predeterminado para el cálculo de referencias de objetos y variantes por valor**  
  
-   Al pasar objetos de código administrado a COM, el contenido del objeto se copia en una nueva variante que crea el contador de referencias usando las reglas definidas en [Cálculo de referencias de objetos para variantes](#cpcondefaultmarshalingforobjectsanchor3).  Los cambios realizados en la variante en el lado no administrado no se vuelven a propagar al objeto original al volver de la llamada.  
  
-   Al pasar variantes de COM a código administrado, el contenido de la variante se copia en un objeto recién creado utilizando las reglas definidas en [Cálculo de referencias de variantes para objetos](#cpcondefaultmarshalingforobjectsanchor4).  Los cambios realizados en el objeto en el lado administrado no se vuelven a propagar a la variante original al volver de la llamada.  
  
 **Comportamiento predeterminado para el cálculo de referencias de objetos y variantes por referencia**  
  
 Para propagar los cambios de nuevo al llamador, los parámetros deben pasarse por referencia.  Por ejemplo, puede utilizar la palabra clave **ref** en C\# \(o **ByRef** en el código administrado de Visual Basic\) para pasar parámetros por referencia.  En COM, para pasar los parámetros por referencia se usa un puntero como una **variant \***.  
  
-   Al pasar un objeto a COM por referencia, el contador de referencias crea una nueva variante y copia el contenido de la referencia de objeto a la variante antes de realizar la llamada.  La variante se pasa a la función no administrada, donde el usuario puede cambiar su contenido.  Los cambios realizados en la variante en el lado no administrado se vuelven a propagar al objeto original al volver de la llamada.  Si el tipo de la variante difiere del tipo de la variante pasada a la llamada, los cambios se vuelven a propagar a un objeto de un tipo distinto.  Es decir, el tipo de objeto pasado en la llamada puede diferir del tipo de objeto que devuelve la llamada.  
  
-   Al pasar una variante a código administrado por referencia, el contador de referencias crea un objeto nuevo y copia el contenido de la variante en él antes de realizarse la llamada.  Una referencia al objeto se pasa a la función administrada, donde el usuario puede cambiar el objeto.  Los cambios realizados en el objeto al que se hace referencia se vuelven a propagar a la variante original al volver de la llamada.  Si el tipo del objeto difiere del tipo de objeto pasado en la llamada, el tipo de la variante original se cambia y el valor se propaga de nuevo en la variante.  De nuevo, el tipo de la variante pasado en la llamada puede diferir del tipo de variante que devuelve la llamada.  
  
 **Comportamiento predeterminado para el cálculo de referencias de una variante con la marca VT\_BYREF establecida**  
  
-   Una variante que se pasa a código administrado por valor puede tener el marcador **VT\_BYREF** establecido para indicar que contiene una referencia en lugar de un valor.  En este caso, se siguen calculando las referencias de la variante para un objeto porque la variante se está pasando por valor.  El contador de referencias desreferencia automáticamente el contenido de la variante y la copia en un objeto recién creado antes de realizar la llamada.  Seguidamente, el objeto se pasa a la función administrada; no obstante, al volver de la llamada, el objeto no se vuelve a propagar a la variante original.  Los cambios realizados en el objeto administrado se pierden.  
  
    > [!CAUTION]
    >  No es posible cambiar el valor de una variante pasada por valor, aunque la variante tenga el marcador **VT\_BYREF** establecido.  
  
-   Una variante que se pasa a código administrado por referencia también puede tener el marcador **VT\_BYREF** establecido para indicar que la variante contiene otra referencia.  Si es así, se calculan las referencias de la variante a un objeto **ref**, ya que la variante se pasa por referencia.  El contador de referencias desreferencia automáticamente el contenido de la variante y la copia en un objeto recién creado antes de realizar la llamada.  Al volver de la llamada, el valor del objeto se vuelve a propagar a la referencia dentro de la variante original solo si el objeto es del mismo tipo que el objeto que se pasa.  Es decir, la propagación no cambia el tipo de una variante con la marca **VT\_BYREF** establecida.  Si el tipo del objeto se cambia durante la llamada, se inicia una excepción <xref:System.InvalidCastException> al volver de la llamada.  
  
 En la tabla siguiente se resumen las reglas de propagación para variantes y objetos.  
  
|From|Para|Cambios que se vuelven a propagar|  
|----------|----------|---------------------------------------|  
|**Variant**  *v*|**Object**  *o*|Nunca|  
|**Object**  *o*|**Variant**  *v*|Nunca|  
|**Variant**   ***\****  *pv*|**Ref Object**  *o*|Siempre|  
|**Ref object**  *o*|**Variant**   ***\****  *pv*|Siempre|  
|**Variant**  *v* **\(VT\_BYREF** *&#124;*  **VT\_\*\)**|**Object**  *o*|Nunca|  
|**Variant**  *v* **\(VT\_BYREF** *&#124;*  **VT\_\)**|**Ref Object**  *o*|Sólo si el tipo no ha cambiado.|  
  
## Vea también  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/es-es/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md)