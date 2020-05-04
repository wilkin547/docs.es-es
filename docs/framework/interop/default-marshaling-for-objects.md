---
title: Serialización predeterminada para objetos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: e0de715a3ed33eedf212fc3e0e9930c9cbaa0a38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123592"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="a6f8c-102">Serialización predeterminada para objetos</span><span class="sxs-lookup"><span data-stu-id="a6f8c-102">Default Marshaling for Objects</span></span>

<span data-ttu-id="a6f8c-103">Los parámetros y campos de tipo <xref:System.Object?displayProperty=nameWithType> pueden exponerse a código no administrado como uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="a6f8c-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>

- <span data-ttu-id="a6f8c-104">Una variante cuando el objeto es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-104">A variant when the object is a parameter.</span></span>

- <span data-ttu-id="a6f8c-105">Una interfaz cuando el objeto es un campo de estructura.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-105">An interface when the object is a structure field.</span></span>

<span data-ttu-id="a6f8c-106">Solo la interoperabilidad COM admite la serialización para tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="a6f8c-107">El comportamiento predeterminado consiste en serializar los objetos en variantes de COM.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="a6f8c-108">Estas reglas se aplican solo al tipo **Object** y no se aplican a objetos fuertemente tipados que se derivan de la clase **Object**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>

## <a name="marshaling-options"></a><span data-ttu-id="a6f8c-109">Opciones de serialización</span><span class="sxs-lookup"><span data-stu-id="a6f8c-109">Marshaling Options</span></span>

<span data-ttu-id="a6f8c-110">En la tabla siguiente se muestran las opciones de serialización para el tipo de datos **Object**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-110">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="a6f8c-111">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para serializar objetos.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-111">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>

|<span data-ttu-id="a6f8c-112">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="a6f8c-112">Enumeration type</span></span>|<span data-ttu-id="a6f8c-113">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="a6f8c-113">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="a6f8c-114">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-114">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="a6f8c-115">(valor predeterminado para parámetros)</span><span class="sxs-lookup"><span data-stu-id="a6f8c-115">(default for parameters)</span></span>|<span data-ttu-id="a6f8c-116">Una variante de estilo COM.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-116">A COM-style variant.</span></span>|
|<span data-ttu-id="a6f8c-117">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-117">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="a6f8c-118">Una interfaz **IDispatch** si es posible; de lo contrario, una interfaz **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-118">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|
|<span data-ttu-id="a6f8c-119">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-119">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="a6f8c-120">(valor predeterminado para campos)</span><span class="sxs-lookup"><span data-stu-id="a6f8c-120">(default for fields)</span></span>|<span data-ttu-id="a6f8c-121">Una interfaz **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-121">An **IUnknown** interface.</span></span>|
|<span data-ttu-id="a6f8c-122">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-122">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="a6f8c-123">Una interfaz **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-123">An **IDispatch** interface.</span></span>|

<span data-ttu-id="a6f8c-124">En el ejemplo siguiente se muestra la definición de interfaz administrada para `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-124">The following example shows the managed interface definition for `MarshalObject`.</span></span>

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

<span data-ttu-id="a6f8c-125">En el código siguiente se exporta la interfaz `MarshalObject` a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-125">The following code exports the `MarshalObject` interface to a type library.</span></span>

```cpp
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
> <span data-ttu-id="a6f8c-126">El serializador de interoperabilidad libera automáticamente cualquier objeto asignado dentro de la variante tras la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-126">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>

<span data-ttu-id="a6f8c-127">En el ejemplo siguiente se muestra un tipo de valor con formato.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-127">The following example shows a formatted value type.</span></span>

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

<span data-ttu-id="a6f8c-128">En el código siguiente se exporta el tipo con formato a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-128">The following code exports the formatted type to a type library.</span></span>

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a><span data-ttu-id="a6f8c-129">Serialización de Object en Interface</span><span class="sxs-lookup"><span data-stu-id="a6f8c-129">Marshaling Object to Interface</span></span>

<span data-ttu-id="a6f8c-130">Cuando un objeto se expone a COM como una interfaz, esa interfaz es la interfaz de clase para el tipo administrado <xref:System.Object> (la interfaz **_Object**).</span><span class="sxs-lookup"><span data-stu-id="a6f8c-130">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="a6f8c-131">Esta interfaz tiene el tipo de **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) o **IUnknown** (**UnmanagedType.IUnknown**) en la biblioteca de tipos resultante.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-131">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="a6f8c-132">Los clientes COM pueden invocar dinámicamente los miembros de la clase administrada o cualquier miembro implementado por sus clases derivadas a través de la interfaz **_Object**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-132">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="a6f8c-133">El cliente puede llamar a **QueryInterface** para obtener cualquier otra interfaz implementada explícitamente por el tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-133">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>

## <a name="marshaling-object-to-variant"></a><span data-ttu-id="a6f8c-134">Serialización de Object en Variant</span><span class="sxs-lookup"><span data-stu-id="a6f8c-134">Marshaling Object to Variant</span></span>

<span data-ttu-id="a6f8c-135">Cuando un objeto se serializa en una variante, el tipo de variante interno se determina en tiempo de ejecución, según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6f8c-135">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>

- <span data-ttu-id="a6f8c-136">Si la referencia de objeto es NULL (**Nothing** en Visual Basic), el objeto se serializa en una variante del tipo **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-136">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>

- <span data-ttu-id="a6f8c-137">Si el objeto es una instancia de cualquier tipo enumerado en la tabla siguiente, el tipo de variante resultante se determina mediante las reglas integradas en el serializador y mostradas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-137">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>

- <span data-ttu-id="a6f8c-138">Otros objetos que necesiten controlar explícitamente el comportamiento de serialización pueden implementar la interfaz <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-138">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="a6f8c-139">En ese caso, el tipo de variante se determina por el código de tipo devuelto por el método <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-139">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a6f8c-140">En caso contrario, el objeto se serializa como una variante de tipo **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-140">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>

### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="a6f8c-141">Serialización de tipos de sistema en Variant</span><span class="sxs-lookup"><span data-stu-id="a6f8c-141">Marshaling System Types to Variant</span></span>

<span data-ttu-id="a6f8c-142">En la tabla siguiente se muestran los tipos de objeto administrados y sus tipos de variante COM correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-142">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="a6f8c-143">Estos tipos solo se convierten cuando la firma del método al que se llama es de tipo <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-143">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>

|<span data-ttu-id="a6f8c-144">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="a6f8c-144">Object type</span></span>|<span data-ttu-id="a6f8c-145">Tipo de variante COM</span><span class="sxs-lookup"><span data-stu-id="a6f8c-145">COM variant type</span></span>|
|-----------------|----------------------|
|<span data-ttu-id="a6f8c-146">Referencia de objeto nula (**Nothing** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a6f8c-146">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="a6f8c-147">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-147">**VT_EMPTY**</span></span>|
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-148">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-148">**VT_NULL**</span></span>|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-149">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-149">**VT_ERROR**</span></span>|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-150">**VT_ERROR** con **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-150">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-151">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-151">**VT_DISPATCH**</span></span>|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-152">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-152">**VT_UNKNOWN**</span></span>|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-153">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-153">**VT_CY**</span></span>|
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-154">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-154">**VT_BOOL**</span></span>|
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-155">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-155">**VT_I1**</span></span>|
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-156">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-156">**VT_UI1**</span></span>|
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-157">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-157">**VT_I2**</span></span>|
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-158">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-158">**VT_UI2**</span></span>|
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-159">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-159">**VT_I4**</span></span>|
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-160">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-160">**VT_UI4**</span></span>|
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-161">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-161">**VT_I8**</span></span>|
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-162">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-162">**VT_UI8**</span></span>|
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-163">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-163">**VT_R4**</span></span>|
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-164">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-164">**VT_R8**</span></span>|
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-165">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-165">**VT_DECIMAL**</span></span>|
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-166">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-166">**VT_DATE**</span></span>|
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-167">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-167">**VT_BSTR**</span></span>|
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-168">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-168">**VT_INT**</span></span>|
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-169">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-169">**VT_UINT**</span></span>|
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="a6f8c-170">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-170">**VT_ARRAY**</span></span>|

<span data-ttu-id="a6f8c-171">Con la interfaz `MarshalObject` definida en el ejemplo anterior, en el ejemplo de código siguiente se muestra cómo pasar varios tipos de variantes a un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-171">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>

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

<span data-ttu-id="a6f8c-172">Los tipos COM que no tienen tipos administrados correspondientes se pueden serializar mediante clases contenedoras como <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> y <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-172">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="a6f8c-173">En el ejemplo de código siguiente se muestra cómo usar estos contenedores para pasar varios tipos de variantes a un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-173">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>

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

<span data-ttu-id="a6f8c-174">Las clases contenedoras se definen en el espacio de nombres <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-174">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>

### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="a6f8c-175">Serialización de la interfaz IConvertible en Variant</span><span class="sxs-lookup"><span data-stu-id="a6f8c-175">Marshaling the IConvertible Interface to Variant</span></span>

<span data-ttu-id="a6f8c-176">Otros tipos distintos a los de la sección anterior pueden controlar cómo se serializan mediante la implementación de la interfaz <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-176">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="a6f8c-177">Si el objeto implementa la interfaz **IConvertible**, el tipo de variante COM se determina en tiempo de ejecución por el valor de la enumeración <xref:System.TypeCode> devuelto desde el método <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-177">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a6f8c-178">En la tabla siguiente se muestran los valores posibles para la enumeración **TypeCode** y el tipo de variante COM correspondiente para cada valor.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-178">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>

|<span data-ttu-id="a6f8c-179">TypeCode</span><span class="sxs-lookup"><span data-stu-id="a6f8c-179">TypeCode</span></span>|<span data-ttu-id="a6f8c-180">Tipo de variante COM</span><span class="sxs-lookup"><span data-stu-id="a6f8c-180">COM variant type</span></span>|
|--------------|----------------------|
|<span data-ttu-id="a6f8c-181">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-181">**TypeCode.Empty**</span></span>|<span data-ttu-id="a6f8c-182">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-182">**VT_EMPTY**</span></span>|
|<span data-ttu-id="a6f8c-183">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-183">**TypeCode.Object**</span></span>|<span data-ttu-id="a6f8c-184">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-184">**VT_UNKNOWN**</span></span>|
|<span data-ttu-id="a6f8c-185">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-185">**TypeCode.DBNull**</span></span>|<span data-ttu-id="a6f8c-186">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-186">**VT_NULL**</span></span>|
|<span data-ttu-id="a6f8c-187">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-187">**TypeCode.Boolean**</span></span>|<span data-ttu-id="a6f8c-188">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-188">**VT_BOOL**</span></span>|
|<span data-ttu-id="a6f8c-189">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-189">**TypeCode.Char**</span></span>|<span data-ttu-id="a6f8c-190">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-190">**VT_UI2**</span></span>|
|<span data-ttu-id="a6f8c-191">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-191">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="a6f8c-192">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-192">**VT_I1**</span></span>|
|<span data-ttu-id="a6f8c-193">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-193">**TypeCode.Byte**</span></span>|<span data-ttu-id="a6f8c-194">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-194">**VT_UI1**</span></span>|
|<span data-ttu-id="a6f8c-195">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-195">**TypeCode.Int16**</span></span>|<span data-ttu-id="a6f8c-196">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-196">**VT_I2**</span></span>|
|<span data-ttu-id="a6f8c-197">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-197">**TypeCode.UInt16**</span></span>|<span data-ttu-id="a6f8c-198">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-198">**VT_UI2**</span></span>|
|<span data-ttu-id="a6f8c-199">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-199">**TypeCode.Int32**</span></span>|<span data-ttu-id="a6f8c-200">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-200">**VT_I4**</span></span>|
|<span data-ttu-id="a6f8c-201">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-201">**TypeCode.UInt32**</span></span>|<span data-ttu-id="a6f8c-202">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-202">**VT_UI4**</span></span>|
|<span data-ttu-id="a6f8c-203">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-203">**TypeCode.Int64**</span></span>|<span data-ttu-id="a6f8c-204">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-204">**VT_I8**</span></span>|
|<span data-ttu-id="a6f8c-205">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-205">**TypeCode.UInt64**</span></span>|<span data-ttu-id="a6f8c-206">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-206">**VT_UI8**</span></span>|
|<span data-ttu-id="a6f8c-207">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-207">**TypeCode.Single**</span></span>|<span data-ttu-id="a6f8c-208">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-208">**VT_R4**</span></span>|
|<span data-ttu-id="a6f8c-209">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-209">**TypeCode.Double**</span></span>|<span data-ttu-id="a6f8c-210">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-210">**VT_R8**</span></span>|
|<span data-ttu-id="a6f8c-211">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-211">**TypeCode.Decimal**</span></span>|<span data-ttu-id="a6f8c-212">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-212">**VT_DECIMAL**</span></span>|
|<span data-ttu-id="a6f8c-213">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-213">**TypeCode.DateTime**</span></span>|<span data-ttu-id="a6f8c-214">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-214">**VT_DATE**</span></span>|
|<span data-ttu-id="a6f8c-215">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-215">**TypeCode.String**</span></span>|<span data-ttu-id="a6f8c-216">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-216">**VT_BSTR**</span></span>|
|<span data-ttu-id="a6f8c-217">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-217">Not supported.</span></span>|<span data-ttu-id="a6f8c-218">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-218">**VT_INT**</span></span>|
|<span data-ttu-id="a6f8c-219">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-219">Not supported.</span></span>|<span data-ttu-id="a6f8c-220">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-220">**VT_UINT**</span></span>|
|<span data-ttu-id="a6f8c-221">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-221">Not supported.</span></span>|<span data-ttu-id="a6f8c-222">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-222">**VT_ARRAY**</span></span>|
|<span data-ttu-id="a6f8c-223">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-223">Not supported.</span></span>|<span data-ttu-id="a6f8c-224">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-224">**VT_RECORD**</span></span>|
|<span data-ttu-id="a6f8c-225">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-225">Not supported.</span></span>|<span data-ttu-id="a6f8c-226">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-226">**VT_CY**</span></span>|
|<span data-ttu-id="a6f8c-227">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-227">Not supported.</span></span>|<span data-ttu-id="a6f8c-228">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-228">**VT_VARIANT**</span></span>|

<span data-ttu-id="a6f8c-229">El valor de la variante COM se determina realizando una llamada a la interfaz **IConvertible.To** *Tipo*, donde **To** *Tipo* es la rutina de conversión que se corresponde con el tipo que se devolvió desde **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-229">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="a6f8c-230">Por ejemplo, un objeto que devuelve **TypeCode.Double** de **IConvertible.GetTypeCode** se serializa como una variante COM de tipo **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-230">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="a6f8c-231">Puede obtener el valor de la variante (almacenado en el campo **dblVal** de la variante COM) si convierte a la interfaz **IConvertible** y llama al método <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-231">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>

## <a name="marshaling-variant-to-object"></a><span data-ttu-id="a6f8c-232">Serialización de Variant en Object</span><span class="sxs-lookup"><span data-stu-id="a6f8c-232">Marshaling Variant to Object</span></span>

<span data-ttu-id="a6f8c-233">Al serializar una variante en un objeto, el tipo y, a veces, el valor de la variante serializada determina el tipo de objeto generado.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-233">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="a6f8c-234">En la siguiente tabla se identifica cada tipo de variante y el tipo de objeto correspondiente que el serializador crea cuando se pasa una variante desde COM a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-234">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>

|<span data-ttu-id="a6f8c-235">Tipo de variante COM</span><span class="sxs-lookup"><span data-stu-id="a6f8c-235">COM variant type</span></span>|<span data-ttu-id="a6f8c-236">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="a6f8c-236">Object type</span></span>|
|----------------------|-----------------|
|<span data-ttu-id="a6f8c-237">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-237">**VT_EMPTY**</span></span>|<span data-ttu-id="a6f8c-238">Referencia de objeto nula (**Nothing** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a6f8c-238">Null object reference (**Nothing** in Visual Basic).</span></span>|
|<span data-ttu-id="a6f8c-239">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-239">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-240">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-240">**VT_DISPATCH**</span></span>|<span data-ttu-id="a6f8c-241">**System.__ComObject** o null si (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="a6f8c-241">**System.__ComObject** or null if (pdispVal == null)</span></span>|
|<span data-ttu-id="a6f8c-242">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-242">**VT_UNKNOWN**</span></span>|<span data-ttu-id="a6f8c-243">**System.__ComObject** o null si (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="a6f8c-243">**System.__ComObject** or null if (punkVal == null)</span></span>|
|<span data-ttu-id="a6f8c-244">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-244">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-245">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-245">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-246">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-246">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-247">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-247">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-248">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-248">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-249">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-249">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-250">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-250">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-251">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-251">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-252">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-252">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-253">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-253">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-254">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-254">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-255">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-255">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-256">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-256">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-257">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-257">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-258">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-258">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-259">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-259">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-260">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-260">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-261">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-261">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-262">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-262">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="a6f8c-263">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-263">**VT_RECORD**</span></span>|<span data-ttu-id="a6f8c-264">Tipo de valor de conversión boxing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-264">Corresponding boxed value type.</span></span>|
|<span data-ttu-id="a6f8c-265">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-265">**VT_VARIANT**</span></span>|<span data-ttu-id="a6f8c-266">No se admite.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-266">Not supported.</span></span>|

<span data-ttu-id="a6f8c-267">Es posible que los tipos de variante que se pasan desde COM a código administrado y después otra vez a COM no conserven el mismo tipo de variante para la duración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-267">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="a6f8c-268">Tenga en cuenta lo que sucede cuando una variante de tipo **VT_DISPATCH** se pasa desde COM a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-268">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="a6f8c-269">Durante la serialización, la variante se convierte en un <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-269">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a6f8c-270">Si después se pasa **Object** a COM, se vuelve a serializar en una variante de tipo **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-270">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="a6f8c-271">No hay ninguna garantía de que la variante que se genera cuando se serializa un objeto desde código administrado a COM sea del mismo tipo que la variante usada inicialmente para generar el objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-271">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>

## <a name="marshaling-byref-variants"></a><span data-ttu-id="a6f8c-272">Serialización de variantes ByRef</span><span class="sxs-lookup"><span data-stu-id="a6f8c-272">Marshaling ByRef Variants</span></span>

<span data-ttu-id="a6f8c-273">Aunque las variantes se pueden pasar por valor o por referencia, la marca **VT_BYREF** también se puede usar con cualquier tipo de variante para indicar que el contenido de la variante se está pasando por referencia en lugar de por valor.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-273">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="a6f8c-274">La diferencia entre serializar variantes por referencia y serializar una variante con la marca **VT_BYREF** establecida puede resultar confusa.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-274">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="a6f8c-275">En la siguiente ilustración se explican las diferencias:</span><span class="sxs-lookup"><span data-stu-id="a6f8c-275">The following illustration clarifies the differences:</span></span>

<span data-ttu-id="a6f8c-276">![Diagrama en el que se muestra la variante que se pasa en la pila.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span><span class="sxs-lookup"><span data-stu-id="a6f8c-276">![Diagram that shows variant passed on the stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span></span>
<span data-ttu-id="a6f8c-277">Variantes pasadas por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a6f8c-277">Variants passed by value and by reference</span></span>

<span data-ttu-id="a6f8c-278">**Comportamiento predeterminado para la serialización de objetos y variantes por valor**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-278">**Default behavior for marshaling objects and variants by value**</span></span>

- <span data-ttu-id="a6f8c-279">Cuando se pasan objetos desde código administrado a COM, el contenido del objeto se copia en una nueva variante creada por el serializador mediante las reglas definidas en [Serialización de Object en Variant](#marshaling-object-to-variant).</span><span class="sxs-lookup"><span data-stu-id="a6f8c-279">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="a6f8c-280">Los cambios realizados en la variante en el lado no administrado no se propagan al objeto original en la devolución de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-280">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>

- <span data-ttu-id="a6f8c-281">Al pasar variantes de COM a código administrado, el contenido de la variante se copia en un objeto recién creado, con las reglas definidas en [Serialización de Variant en Object](#marshaling-variant-to-object).</span><span class="sxs-lookup"><span data-stu-id="a6f8c-281">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="a6f8c-282">Los cambios realizados en el objeto en el lado no administrado no se propagan a la variante original en la devolución de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-282">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>

<span data-ttu-id="a6f8c-283">**Comportamiento predeterminado para la serialización de objetos y variantes por referencia**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-283">**Default behavior for marshaling objects and variants by reference**</span></span>

<span data-ttu-id="a6f8c-284">Para propagar los cambios de vuelta al autor de la llamada, los parámetros deben pasarse por referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-284">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="a6f8c-285">Por ejemplo, puede usar la palabra clave **ref** de C# (o **ByRef** en código administrado de Visual Basic) para pasar parámetros por referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-285">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="a6f8c-286">En COM, los parámetros de referencia se pasan con un puntero como una **variante \*** .</span><span class="sxs-lookup"><span data-stu-id="a6f8c-286">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>

- <span data-ttu-id="a6f8c-287">Cuando se pasa un objeto a COM por referencia, el serializador crea una variante y copia el contenido de la referencia de objeto en la variante antes de que se realice la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-287">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="a6f8c-288">La variante se pasa a la función no administrada, donde el usuario tiene libertad para cambiar el contenido de la variante.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-288">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="a6f8c-289">En la devolución de la llamada, los cambios realizados en la variante en el lado no administrado se propagan al objeto original.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-289">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="a6f8c-290">Si el tipo de la variante difiere del tipo de la variante que se pasa a la llamada, los cambios se propagan a un objeto de un tipo diferente.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-290">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="a6f8c-291">Es decir, el tipo del objeto pasado en la llamada puede diferir del tipo del objeto devuelto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-291">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>

- <span data-ttu-id="a6f8c-292">Cuando se pasa una variante por referencia a código administrado, el serializador crea un objeto y copia el contenido de la variante en el objeto antes de que se realice la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-292">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="a6f8c-293">Se pasa una referencia al objeto a la función administrada, donde el usuario tiene libertad para cambiar el contenido del objeto.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-293">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="a6f8c-294">En la devolución de la llamada, los cambios realizados en el objeto al que se hace referencia se propagan a la variante original.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-294">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="a6f8c-295">Si el tipo del objeto difiere del tipo del objeto pasado en la llamada, el tipo de la variante original se cambia y el valor se propaga a la variante.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-295">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="a6f8c-296">Como antes, el tipo de la variante pasada en la llamada puede diferir del tipo de la variante devuelta de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-296">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>

 <span data-ttu-id="a6f8c-297">**Comportamiento predeterminado para serializar una variante con la marca VT_BYREF establecida**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-297">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>

- <span data-ttu-id="a6f8c-298">Una variante que se pasa a código administrado por valor puede tener la marca **VT_BYREF** establecida para indicar que la variante contiene una referencia en lugar de un valor.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-298">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="a6f8c-299">En este caso, la variante se sigue serializando en un objeto porque la variante se pasa por valor.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-299">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="a6f8c-300">El serializador desreferencia automáticamente el contenido de la variante y la copia en un objeto recién creado antes de realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-300">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="a6f8c-301">Después, el objeto se pasa a la función administrada; pero en la devolución de la llamada, el objeto no se propaga a la variante original.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-301">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="a6f8c-302">Se perderán los cambios realizados en el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-302">Changes made to the managed object are lost.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a6f8c-303">No hay ninguna manera de cambiar el valor de una variante pasada por valor, aunque la variante tenga establecida la marca **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-303">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>

- <span data-ttu-id="a6f8c-304">Una variante que se pasa a código administrado por referencia también puede tener la marca **VT_BYREF** establecida para indicar que la variante contiene otra referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-304">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="a6f8c-305">En ese caso, la variante se serializa en un objeto **ref** porque la variante se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-305">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="a6f8c-306">El serializador desreferencia automáticamente el contenido de la variante y la copia en un objeto recién creado antes de realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="a6f8c-307">En la devolución de la llamada, el valor del objeto se propaga a la referencia dentro de la variante original solo si el objeto es del mismo tipo que el objeto que se pasa.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-307">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="a6f8c-308">Es decir, la propagación no cambia el tipo de una variante con la marca **VT_BYREF** establecida.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-308">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="a6f8c-309">Si el tipo del objeto se cambia durante la llamada, se inicia una excepción <xref:System.InvalidCastException> en la devolución de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-309">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>

<span data-ttu-id="a6f8c-310">En la tabla siguiente se resumen las reglas de propagación para variantes y objetos.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-310">The following table summarizes the propagation rules for variants and objects.</span></span>

|<span data-ttu-id="a6f8c-311">De</span><span class="sxs-lookup"><span data-stu-id="a6f8c-311">From</span></span>|<span data-ttu-id="a6f8c-312">En</span><span class="sxs-lookup"><span data-stu-id="a6f8c-312">To</span></span>|<span data-ttu-id="a6f8c-313">Los cambios se propagan</span><span class="sxs-lookup"><span data-stu-id="a6f8c-313">Changes propagated back</span></span>|
|----------|--------|-----------------------------|
|<span data-ttu-id="a6f8c-314">**Variante**  *v*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-314">**Variant**  *v*</span></span>|<span data-ttu-id="a6f8c-315">**Objeto**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-315">**Object**  *o*</span></span>|<span data-ttu-id="a6f8c-316">Nunca</span><span class="sxs-lookup"><span data-stu-id="a6f8c-316">Never</span></span>|
|<span data-ttu-id="a6f8c-317">**Objeto**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-317">**Object**  *o*</span></span>|<span data-ttu-id="a6f8c-318">**Variante**  *v*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-318">**Variant**  *v*</span></span>|<span data-ttu-id="a6f8c-319">Nunca</span><span class="sxs-lookup"><span data-stu-id="a6f8c-319">Never</span></span>|
|<span data-ttu-id="a6f8c-320">**Variante**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-320">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="a6f8c-321">**Objeto de referencia**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-321">**Ref Object**  *o*</span></span>|<span data-ttu-id="a6f8c-322">Siempre</span><span class="sxs-lookup"><span data-stu-id="a6f8c-322">Always</span></span>|
|<span data-ttu-id="a6f8c-323">**Objeto de referencia**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-323">**Ref object**  *o*</span></span>|<span data-ttu-id="a6f8c-324">**Variante**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-324">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="a6f8c-325">Siempre</span><span class="sxs-lookup"><span data-stu-id="a6f8c-325">Always</span></span>|
|<span data-ttu-id="a6f8c-326">**Variante**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-326">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="a6f8c-327">**Objeto**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-327">**Object**  *o*</span></span>|<span data-ttu-id="a6f8c-328">Nunca</span><span class="sxs-lookup"><span data-stu-id="a6f8c-328">Never</span></span>|
|<span data-ttu-id="a6f8c-329">**Variante**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="a6f8c-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="a6f8c-330">**Objeto de referencia**  *o*</span><span class="sxs-lookup"><span data-stu-id="a6f8c-330">**Ref Object**  *o*</span></span>|<span data-ttu-id="a6f8c-331">Solo si el tipo no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="a6f8c-331">Only if the type has not changed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a6f8c-332">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6f8c-332">See also</span></span>

- [<span data-ttu-id="a6f8c-333">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="a6f8c-333">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="a6f8c-334">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="a6f8c-334">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="a6f8c-335">[Atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a6f8c-335">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="a6f8c-336">Copiar y fijar</span><span class="sxs-lookup"><span data-stu-id="a6f8c-336">Copying and Pinning</span></span>](copying-and-pinning.md)
