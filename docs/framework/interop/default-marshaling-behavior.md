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
ms.openlocfilehash: 3e18bb5c4caa43a8e951eed3fc6992ec1b2d2afb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256664"
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="a825d-104">Comportamiento de serialización predeterminado</span><span class="sxs-lookup"><span data-stu-id="a825d-104">Default Marshaling Behavior</span></span>

<span data-ttu-id="a825d-105">La serialización de interoperabilidad funciona con reglas que dictan cómo se comportan los datos asociados con parámetros de método cuando pasan entre memoria administrada y no administrada.</span><span class="sxs-lookup"><span data-stu-id="a825d-105">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="a825d-106">Estas reglas integradas controlan las actividades de serialización como transformaciones de tipos de datos, si un destinatario puede cambiar los datos que recibe y devolver esos cambios al llamador, y en qué circunstancias el serializador proporciona optimizaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a825d-106">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="a825d-107">En esta sección se identifican las características predeterminadas de comportamiento del servicio de serialización de interoperabilidad,</span><span class="sxs-lookup"><span data-stu-id="a825d-107">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="a825d-108">y se muestra información detallada sobre la serialización de matrices, tipos booleanos, tipos de caracteres, delegados, clases, objetos, cadenas y estructuras.</span><span class="sxs-lookup"><span data-stu-id="a825d-108">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a825d-109">No se admite la serialización de tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="a825d-109">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="a825d-110">Para más información, vea [Interoperar mediante tipos genéricos](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a825d-110">For more information see, [Interoperating Using Generic Types](/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="a825d-111">Administración de memoria con el serializador de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="a825d-111">Memory management with the interop marshaler</span></span>  

 <span data-ttu-id="a825d-112">El serializador de interoperabiliad siempre intenta liberar memoria asignada por código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-112">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="a825d-113">Este comportamiento cumple con las reglas de administración de memoria COM, pero difiere de las reglas que rigen C++ nativo.</span><span class="sxs-lookup"><span data-stu-id="a825d-113">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="a825d-114">Se puede producir confusión si se prevé un comportamiento de C++ nativo (sin liberación de memoria) al usar invocación de plataforma, que automáticamente libera memoria para los punteros.</span><span class="sxs-lookup"><span data-stu-id="a825d-114">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="a825d-115">Por ejemplo, la llamada al siguiente método no administrado desde una DLL de C++ no libera automáticamente memoria.</span><span class="sxs-lookup"><span data-stu-id="a825d-115">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="a825d-116">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="a825d-116">Unmanaged signature</span></span>  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="a825d-117">Sin embargo, si define el método como un prototipo de invocación de plataforma, reemplaza cada tipo **BSTR** por un tipo <xref:System.String> y llama a `MethodOne`, Common Language Runtime intenta liberar `b` dos veces.</span><span class="sxs-lookup"><span data-stu-id="a825d-117">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="a825d-118">Puede cambiar el comportamiento de serialización mediante tipos <xref:System.IntPtr> en lugar de tipos **String**.</span><span class="sxs-lookup"><span data-stu-id="a825d-118">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="a825d-119">El tiempo de ejecución usa siempre el método **CoTaskMemFree** para liberar memoria.</span><span class="sxs-lookup"><span data-stu-id="a825d-119">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="a825d-120">Si la memoria con la que está trabajando no se asignó con el método **CoTaskMemAlloc**, debe usar un **IntPtr** y liberar la memoria manualmente mediante el método adecuado.</span><span class="sxs-lookup"><span data-stu-id="a825d-120">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="a825d-121">De forma similar, puede evitar la liberación automática de la memoria en situaciones donde nunca se debería liberar, como al usar la función **GetCommandLine** de Kernel32.dll, que devuelve un puntero a la memoria del kernel.</span><span class="sxs-lookup"><span data-stu-id="a825d-121">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="a825d-122">Para obtener más información sobre cómo liberar memoria manualmente, vea el [ejemplo sobre búferes](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a825d-122">For details on manually freeing memory, see the [Buffers Sample](/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="a825d-123">Serialización predeterminada para clases</span><span class="sxs-lookup"><span data-stu-id="a825d-123">Default marshaling for classes</span></span>  

 <span data-ttu-id="a825d-124">Las clases solo se pueden serializar con la interoperabilidad COM y siempre se serializan como interfaces.</span><span class="sxs-lookup"><span data-stu-id="a825d-124">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="a825d-125">En algunos casos, la interfaz usada para calcular las referencias de la clase se conoce como interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="a825d-125">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="a825d-126">Para obtener información sobre cómo reemplazar la interfaz de clase por una interfaz de su elección, consulte [Presentar la interfaz de clase](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span><span class="sxs-lookup"><span data-stu-id="a825d-126">For information about overriding the class interface with an interface of your choice, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="a825d-127">Pasar clases a COM</span><span class="sxs-lookup"><span data-stu-id="a825d-127">Passing Classes to COM</span></span>  

 <span data-ttu-id="a825d-128">Cuando una clase administrada se pasa a COM, el serializador de interoperabilidad automáticamente encapsula la clase con un proxy COM y pasa la interfaz de clase generada por el proxy a la llamada de método COM.</span><span class="sxs-lookup"><span data-stu-id="a825d-128">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="a825d-129">El proxy delega entonces todas las llamadas en la interfaz de clase al objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-129">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="a825d-130">El proxy también expone otras interfaces que no están implementadas explícitamente por la clase.</span><span class="sxs-lookup"><span data-stu-id="a825d-130">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="a825d-131">El proxy implementa automáticamente interfaces como **IUnknown** e **IDispatch** en nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="a825d-131">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="a825d-132">Pasar clases a código de .NET</span><span class="sxs-lookup"><span data-stu-id="a825d-132">Passing Classes to .NET Code</span></span>  

 <span data-ttu-id="a825d-133">Las coclases no suelen usarse como argumentos de método en COM.</span><span class="sxs-lookup"><span data-stu-id="a825d-133">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="a825d-134">En lugar de la coclase, normalmente se pasa una interfaz predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a825d-134">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="a825d-135">Cuando una interfaz se pasa a código administrado, el serializador de interoperabilidad es responsable de encapsular la interfaz en el contenedor adecuado y pasar este contenedor al método administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-135">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="a825d-136">Determinar qué contenedor se usará puede resultar difícil.</span><span class="sxs-lookup"><span data-stu-id="a825d-136">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="a825d-137">Cada instancia de un objeto COM tiene un solo contenedor, independientemente de cuántas interfaces implemente el objeto.</span><span class="sxs-lookup"><span data-stu-id="a825d-137">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="a825d-138">Por ejemplo, un único objeto COM que implementa cinco interfaces distintas tiene un solo contenedor.</span><span class="sxs-lookup"><span data-stu-id="a825d-138">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="a825d-139">El mismo contenedor expone las cinco interfaces.</span><span class="sxs-lookup"><span data-stu-id="a825d-139">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="a825d-140">Si se crean dos instancias del objeto COM, también se crean dos instancias del contenedor.</span><span class="sxs-lookup"><span data-stu-id="a825d-140">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="a825d-141">Para que el contenedor mantenga el mismo tipo a lo largo del tiempo, el serializador de interoperabilidad debe identificar el contenedor correcto la primera vez que una interfaz expuesta por el objeto se pasa a través del serializador.</span><span class="sxs-lookup"><span data-stu-id="a825d-141">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="a825d-142">El serializador identifica el objeto examinando una de las interfaces que implementa el objeto.</span><span class="sxs-lookup"><span data-stu-id="a825d-142">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="a825d-143">Por ejemplo, el serializador determina que el contenedor de clase se debe usar para encapsular la interfaz que se pasó a código administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-143">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="a825d-144">Cuando la interfaz pasa primero por el serializador, este comprueba si la interfaz procede de un objeto conocido.</span><span class="sxs-lookup"><span data-stu-id="a825d-144">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="a825d-145">Esta comprobación se produce en dos situaciones:</span><span class="sxs-lookup"><span data-stu-id="a825d-145">This check occurs in two situations:</span></span>  
  
- <span data-ttu-id="a825d-146">Se está implementando una interfaz mediante otro objeto administrado que se pasó a COM en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="a825d-146">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="a825d-147">El serializador puede identificar inmediatamente las interfaces expuestas por los objetos administrados y es capaz de hacer coincidir la interfaz con el objeto administrado que proporciona la implementación.</span><span class="sxs-lookup"><span data-stu-id="a825d-147">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="a825d-148">El objeto administrado se pasa a continuación al método y no se necesita ningún contenedor.</span><span class="sxs-lookup"><span data-stu-id="a825d-148">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
- <span data-ttu-id="a825d-149">Un objeto que ya se ha encapsulado se está implementando en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a825d-149">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="a825d-150">Para determinar si este es el caso, el serializador consulta al objeto su interfaz **IUnknown** y compara la interfaz devuelta con las interfaces de otros objetos que ya están encapsulados.</span><span class="sxs-lookup"><span data-stu-id="a825d-150">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="a825d-151">Si la interfaz es la misma que la de otro contenedor, los objetos tienen la misma identidad y el contenedor existente se pasa al método.</span><span class="sxs-lookup"><span data-stu-id="a825d-151">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="a825d-152">Si no es una interfaz de un objeto conocido, el serializador realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a825d-152">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1. <span data-ttu-id="a825d-153">El serializador consulta al objeto la interfaz **IProvideClassInfo2**.</span><span class="sxs-lookup"><span data-stu-id="a825d-153">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="a825d-154">Si se proporciona, el serializador usa el CLSID devuelto de **IProvideClassInfo2.GetGUID** para identificar la coclase que proporciona la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a825d-154">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="a825d-155">Con el CLSID, el serializador puede ubicar el contenedor en el Registro si previamente se ha registrado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a825d-155">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2. <span data-ttu-id="a825d-156">El serializador consulta a la interfaz la interfaz **IProvideClassInfo**.</span><span class="sxs-lookup"><span data-stu-id="a825d-156">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="a825d-157">Si se proporciona, el serializador usa el **ITypeInfo** devuelto desde **IProvideClassInfo.GetClassinfo** para determinar el CLSID de la clase que expone la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a825d-157">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="a825d-158">El serializador puede usar el CLSID para buscar los metadatos del contenedor.</span><span class="sxs-lookup"><span data-stu-id="a825d-158">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3. <span data-ttu-id="a825d-159">Si el serializador sigue sin poder identificar la clase, encapsula la interfaz en una clase de contenedor genérica denominada **System.__ComObject**.</span><span class="sxs-lookup"><span data-stu-id="a825d-159">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="a825d-160">Serialización predeterminada para delegados</span><span class="sxs-lookup"><span data-stu-id="a825d-160">Default marshaling for delegates</span></span>  

 <span data-ttu-id="a825d-161">Un delegado administrado se serializa como una interfaz COM o como un puntero de función según el mecanismo de llamada:</span><span class="sxs-lookup"><span data-stu-id="a825d-161">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
- <span data-ttu-id="a825d-162">Para invocación de plataforma, se serializa un delegado como un puntero de función no administrada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a825d-162">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
- <span data-ttu-id="a825d-163">Para interoperabilidad COM, se serializa un delegado como una interfaz COM de tipo **_Delegate** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a825d-163">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="a825d-164">La interfaz **_Delegate** se define en la biblioteca de tipos Mscorlib.tlb y contiene el método <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>, que permite llamar al método al que hace referencia el delegado.</span><span class="sxs-lookup"><span data-stu-id="a825d-164">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="a825d-165">En la siguiente tabla se muestran las opciones de serialización para el tipo de datos de delegado administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-165">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="a825d-166">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para serializar los delegados.</span><span class="sxs-lookup"><span data-stu-id="a825d-166">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="a825d-167">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="a825d-167">Enumeration type</span></span>|<span data-ttu-id="a825d-168">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="a825d-168">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="a825d-169">**UnmanagedType.FunctionPtr**</span><span class="sxs-lookup"><span data-stu-id="a825d-169">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="a825d-170">Es un puntero de función no administrada.</span><span class="sxs-lookup"><span data-stu-id="a825d-170">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="a825d-171">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="a825d-171">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="a825d-172">Una interfaz de tipo **_Delegate**, como se define en Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="a825d-172">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="a825d-173">Considere el siguiente código de ejemplo en el que los métodos de `DelegateTestInterface` se exportan a una biblioteca de tipos COM.</span><span class="sxs-lookup"><span data-stu-id="a825d-173">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="a825d-174">Observe que solo los delegados marcados con la palabra clave **ref** (o **ByRef**) se pasan como parámetros In/Out.</span><span class="sxs-lookup"><span data-stu-id="a825d-174">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
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
  
### <a name="type-library-representation"></a><span data-ttu-id="a825d-175">Representación de biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="a825d-175">Type library representation</span></span>  
  
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
  
 <span data-ttu-id="a825d-176">Se puede desreferenciar un puntero de función, igual que con cualquier otro puntero de función no administrada.</span><span class="sxs-lookup"><span data-stu-id="a825d-176">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  

<span data-ttu-id="a825d-177">En este ejemplo, al serializar los dos delegados como <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, el resultado es un elemento `int` y un puntero a un elemento `int`.</span><span class="sxs-lookup"><span data-stu-id="a825d-177">In this example, when the two delegates are marshaled as <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType>, the result is an `int` and a pointer to an `int`.</span></span> <span data-ttu-id="a825d-178">Como los tipos de delegado se serializan, aquí `int` representa un puntero a un valor void (`void*`), que es la dirección del delegado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a825d-178">Because delegate types are being marshaled, `int` here represents a pointer to a void (`void*`), which is the address of the delegate in memory.</span></span> <span data-ttu-id="a825d-179">En otras palabras, este resultado es específico para los sistemas Windows de 32 bits, ya que `int` aquí representa el tamaño del puntero de función.</span><span class="sxs-lookup"><span data-stu-id="a825d-179">In other words, this result is specific to 32-bit Windows systems, since `int` here represents the size of the function pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="a825d-180">Una referencia al puntero de función para un delegado administrado mantenido por código no administrado no impide que Common Language Runtime realice la recolección de elementos no utilizados en el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-180">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="a825d-181">Por ejemplo, el código siguiente es incorrecto porque la referencia al objeto `cb`, que se pasa al método `SetChangeHandler`, no mantiene a `cb` activo más allá de la vida del método `Test`.</span><span class="sxs-lookup"><span data-stu-id="a825d-181">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="a825d-182">Una vez recopilados los elementos no utilizados del objeto `cb`, el puntero de función pasado a `SetChangeHandler` deja de ser válido.</span><span class="sxs-lookup"><span data-stu-id="a825d-182">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
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
  
 <span data-ttu-id="a825d-183">Para compensar la recolección inesperada de elementos no utilizados, el llamador debe asegurarse de que el objeto `cb` se mantiene activo mientras el puntero de función no administrada está en uso.</span><span class="sxs-lookup"><span data-stu-id="a825d-183">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="a825d-184">Opcionalmente, puede hacer que el código no administrado le notifique al código administrado si el puntero de función ya no es necesario, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a825d-184">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
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
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="a825d-185">Serialización predeterminada para tipos de valor</span><span class="sxs-lookup"><span data-stu-id="a825d-185">Default marshaling for value types</span></span>  

 <span data-ttu-id="a825d-186">La mayoría de los tipos de valor, como enteros y números de punto flotante, [pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) y no requieren serialización.</span><span class="sxs-lookup"><span data-stu-id="a825d-186">Most value types, such as integers and floating-point numbers, are [blittable](blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="a825d-187">Otros tipos que [no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) tienen representaciones distintas en memoria administrada y no administrada, y requieren serialización.</span><span class="sxs-lookup"><span data-stu-id="a825d-187">Other [non-blittable](blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="a825d-188">Hay también otros tipos que requieren un formato explícito en el límite de interoperación.</span><span class="sxs-lookup"><span data-stu-id="a825d-188">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="a825d-189">En esta sección se proporciona información sobre los tipos de valor con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="a825d-189">This section provides information on the following formatted value types:</span></span>  
  
- [<span data-ttu-id="a825d-190">Tipos de valor utilizados en la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="a825d-190">Value Types Used in Platform Invoke</span></span>](#value-types-used-in-platform-invoke)  
  
- [<span data-ttu-id="a825d-191">Tipos de valor utilizados en la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="a825d-191">Value Types Used in COM Interop</span></span>](#value-types-used-in-com-interop)  
  
 <span data-ttu-id="a825d-192">Además de describir tipos con formato, en este tema se identifican [tipos de valor System](#system-value-types) que tienen un comportamiento de serialización poco habitual.</span><span class="sxs-lookup"><span data-stu-id="a825d-192">In addition to describing formatted types, this topic identifies [System Value Types](#system-value-types) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="a825d-193">Un tipo con formato es un tipo complejo que contiene información que controla explícitamente la distribución de sus miembros en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a825d-193">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="a825d-194">La información de distribución de miembros se proporciona mediante el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a825d-194">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="a825d-195">La distribución puede ser uno de los siguientes valores de enumeración <xref:System.Runtime.InteropServices.LayoutKind>:</span><span class="sxs-lookup"><span data-stu-id="a825d-195">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
- <span data-ttu-id="a825d-196">**LayoutKind.Auto**</span><span class="sxs-lookup"><span data-stu-id="a825d-196">**LayoutKind.Auto**</span></span>  
  
     <span data-ttu-id="a825d-197">Indica que Common Language Runtime puede volver a ordenar los miembros del tipo para lograr una mayor eficacia.</span><span class="sxs-lookup"><span data-stu-id="a825d-197">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="a825d-198">Sin embargo, cuando un tipo de valor se pasa a código no administrado, la distribución de los miembros es predecible.</span><span class="sxs-lookup"><span data-stu-id="a825d-198">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="a825d-199">Si se intenta serializar automáticamente una estructura de este tipo, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a825d-199">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
- <span data-ttu-id="a825d-200">**LayoutKind.Sequential**</span><span class="sxs-lookup"><span data-stu-id="a825d-200">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="a825d-201">Indica que los miembros del tipo se distribuyen en la memoria no administrada en el mismo orden en que aparecen en la definición de tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-201">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
- <span data-ttu-id="a825d-202">**LayoutKind.Explicit**</span><span class="sxs-lookup"><span data-stu-id="a825d-202">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="a825d-203">Indica que los miembros se distribuyen según el <xref:System.Runtime.InteropServices.FieldOffsetAttribute> proporcionado con cada campo.</span><span class="sxs-lookup"><span data-stu-id="a825d-203">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="a825d-204">Tipos de valor utilizados en la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="a825d-204">Value Types Used in Platform Invoke</span></span>  

 <span data-ttu-id="a825d-205">En el ejemplo siguiente, los tipos `Point` y `Rect` proporcionan información de distribución de miembros mediante **StructLayoutAttribute**.</span><span class="sxs-lookup"><span data-stu-id="a825d-205">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
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
  
 <span data-ttu-id="a825d-206">Al serializar a código no administrado, estos tipos con formato se serializan como estructuras de estilo C.</span><span class="sxs-lookup"><span data-stu-id="a825d-206">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="a825d-207">Esto proporciona una manera sencilla de llamar a una API no administrada que tiene argumentos de estructura.</span><span class="sxs-lookup"><span data-stu-id="a825d-207">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="a825d-208">Por ejemplo, las estructuras `POINT` y `RECT` se pueden pasar a la función **PtInRect** de la API de Microsoft Windows del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a825d-208">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Windows API **PtInRect** function as follows:</span></span>  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="a825d-209">Las estructuras se pueden pasar mediante la siguiente definición de invocación de plataforma:</span><span class="sxs-lookup"><span data-stu-id="a825d-209">You can pass structures using the following platform invoke definition:</span></span>  
  
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
  
 <span data-ttu-id="a825d-210">El tipo de valor `Rect` se debe pasar por referencia porque la API no administrada espera que un puntero a un `RECT` se pase a la función.</span><span class="sxs-lookup"><span data-stu-id="a825d-210">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="a825d-211">El tipo de valor `Point` se pasa por valor porque la API no administrada espera que `POINT` se pase en la pila.</span><span class="sxs-lookup"><span data-stu-id="a825d-211">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="a825d-212">Esta diferencia sutil es muy importante.</span><span class="sxs-lookup"><span data-stu-id="a825d-212">This subtle difference is very important.</span></span> <span data-ttu-id="a825d-213">Las referencias se pasan a código no administrado como punteros.</span><span class="sxs-lookup"><span data-stu-id="a825d-213">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="a825d-214">Los valores se pasan a código no administrado en la pila.</span><span class="sxs-lookup"><span data-stu-id="a825d-214">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a825d-215">Cuando un tipo con formato se serializa como una estructura, solo son accesibles los campos dentro del tipo.</span><span class="sxs-lookup"><span data-stu-id="a825d-215">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="a825d-216">Si el tipo tiene métodos, propiedades o eventos, son inaccesibles desde código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-216">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="a825d-217">Las clases también se pueden serializar a código no administrado como estructuras de estilo C, a condición de que tengan una distribución de miembros fija.</span><span class="sxs-lookup"><span data-stu-id="a825d-217">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="a825d-218">La información de distribución de miembros para una clase también se proporciona con el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a825d-218">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="a825d-219">La diferencia principal entre los tipos de valor con distribución fija y las clases con distribución fija es la forma en la que se serializan a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a825d-219">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="a825d-220">Los tipos de valor se pasan por valor (en la pila) y, por consiguiente, el llamador no ve los cambios realizados por el destinatario en los miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="a825d-220">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="a825d-221">Los tipos de referencia se pasan por referencia (se pasa una referencia al tipo en la pila); en consecuencia, el llamador ve todos los cambios realizados por el destinatario en miembros de un tipo que pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="a825d-221">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a825d-222">Si un tipo de referencia tiene miembros de tipos que no pueden transferirse en bloque de bits, se requiere una conversión doble: la primera vez cuando se pasa un argumento al lado no administrado y la segunda vez en la devolución de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a825d-222">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="a825d-223">Debido a esta sobrecarga adicional, los parámetros In/Out deben aplicarse explícitamente a un argumento si el llamador desea ver los cambios realizados por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="a825d-223">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="a825d-224">En el ejemplo siguiente, la clase `SystemTime` tiene distribución de miembros secuencial y puede pasarse a la función **GetSystemTime** de la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="a825d-224">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Windows API **GetSystemTime** function.</span></span>  
  
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
  
 <span data-ttu-id="a825d-225">La función **GetSystemTime** se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="a825d-225">The **GetSystemTime** function is defined as follows:</span></span>  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="a825d-226">La definición de invocación de plataforma equivalente para **GetSystemTime** es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a825d-226">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
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
  
 <span data-ttu-id="a825d-227">Tenga en cuenta que el argumento `SystemTime` no se tipifica como argumento de referencia porque `SystemTime` es una clase, no un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="a825d-227">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="a825d-228">A diferencia de los tipos de valor, las clases siempre se pasan por referencia.</span><span class="sxs-lookup"><span data-stu-id="a825d-228">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="a825d-229">En el ejemplo de código siguiente se muestra otra clase `Point` que tiene un método denominado `SetXY`.</span><span class="sxs-lookup"><span data-stu-id="a825d-229">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="a825d-230">Puesto que el tipo tiene una distribución secuencial, puede pasarse a código no administrado y serializarse como una estructura.</span><span class="sxs-lookup"><span data-stu-id="a825d-230">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="a825d-231">Sin embargo, el miembro `SetXY` no es invocable desde código no administrado, aunque el objeto se pase por referencia.</span><span class="sxs-lookup"><span data-stu-id="a825d-231">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
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
  
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="a825d-232">Tipos de valor utilizados en la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="a825d-232">Value Types Used in COM Interop</span></span>  

 <span data-ttu-id="a825d-233">Los tipos con formato también pueden pasarse a llamadas de métodos de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="a825d-233">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="a825d-234">De hecho, cuando se exportan a una biblioteca de tipos, los tipos de valor se convierten automáticamente en estructuras.</span><span class="sxs-lookup"><span data-stu-id="a825d-234">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="a825d-235">Como se muestra en el ejemplo siguiente, el tipo de valor `Point` se convierte en una definición de tipo (typedef) con el nombre `Point`.</span><span class="sxs-lookup"><span data-stu-id="a825d-235">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="a825d-236">Todas las referencias al tipo de valor `Point` en otro lugar de la biblioteca de tipos se reemplazan por el typedef `Point`.</span><span class="sxs-lookup"><span data-stu-id="a825d-236">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="a825d-237">**Representación de biblioteca de tipos**</span><span class="sxs-lookup"><span data-stu-id="a825d-237">**Type library representation**</span></span>  
  
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
  
 <span data-ttu-id="a825d-238">Las mismas reglas usadas para serializar valores y referencias para llamadas de invocación de plataforma se usan al serializar a través de interfaces COM.</span><span class="sxs-lookup"><span data-stu-id="a825d-238">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="a825d-239">Por ejemplo, cuando una instancia del tipo de valor `Point` se pasa de .NET Framework a COM, `Point` se pasa por valor.</span><span class="sxs-lookup"><span data-stu-id="a825d-239">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="a825d-240">Si el tipo de valor `Point` se pasa por referencia, un puntero a un `Point` se pasa en la pila.</span><span class="sxs-lookup"><span data-stu-id="a825d-240">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="a825d-241">El serializador de interoperabilidad no admite niveles superiores de direccionamiento indirecto (**Point** \*\*) en ninguna dirección.</span><span class="sxs-lookup"><span data-stu-id="a825d-241">The interop marshaler does not support higher levels of indirection (**Point** \*\*) in either direction.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a825d-242">Las estructuras que tienen el valor de enumeración <xref:System.Runtime.InteropServices.LayoutKind> establecido en **Explicit** no se pueden usar en la interoperabilidad COM porque la biblioteca de tipos exportada no puede expresar una distribución explícita.</span><span class="sxs-lookup"><span data-stu-id="a825d-242">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
### <a name="system-value-types"></a><span data-ttu-id="a825d-243">Tipos de valor System</span><span class="sxs-lookup"><span data-stu-id="a825d-243">System Value Types</span></span>  

 <span data-ttu-id="a825d-244">El espacio de nombres <xref:System> tiene varios tipos de valor que representan la forma de conversión boxing de los tipos primitivos en runtime.</span><span class="sxs-lookup"><span data-stu-id="a825d-244">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="a825d-245">Por ejemplo, la estructura <xref:System.Int32?displayProperty=nameWithType> de tipo de valor representa la forma de conversión boxing de **ELEMENT_TYPE_I4**.</span><span class="sxs-lookup"><span data-stu-id="a825d-245">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="a825d-246">En lugar de serializar estos tipos como estructuras, como otros tipos con formato, se serializan de la misma forma que los tipos primitivos a los que aplican conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="a825d-246">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="a825d-247">Por tanto, **System.Int32** se serializa como **ELEMENT_TYPE_I4** en lugar de como una estructura que contiene un único miembro de tipo **long**.</span><span class="sxs-lookup"><span data-stu-id="a825d-247">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="a825d-248">La tabla siguiente contiene una lista de los tipos de valor en el espacio de nombres **System** que son representaciones de conversión boxing de tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="a825d-248">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="a825d-249">Tipo de valor System</span><span class="sxs-lookup"><span data-stu-id="a825d-249">System value type</span></span>|<span data-ttu-id="a825d-250">Tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="a825d-250">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="a825d-251">**ELEMENT_TYPE_BOOLEAN**</span><span class="sxs-lookup"><span data-stu-id="a825d-251">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="a825d-252">**ELEMENT_TYPE_I1**</span><span class="sxs-lookup"><span data-stu-id="a825d-252">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="a825d-253">**ELEMENT_TYPE_UI1**</span><span class="sxs-lookup"><span data-stu-id="a825d-253">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="a825d-254">**ELEMENT_TYPE_CHAR**</span><span class="sxs-lookup"><span data-stu-id="a825d-254">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="a825d-255">**ELEMENT_TYPE_I2**</span><span class="sxs-lookup"><span data-stu-id="a825d-255">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="a825d-256">**ELEMENT_TYPE_U2**</span><span class="sxs-lookup"><span data-stu-id="a825d-256">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="a825d-257">**ELEMENT_TYPE_I4**</span><span class="sxs-lookup"><span data-stu-id="a825d-257">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="a825d-258">**ELEMENT_TYPE_U4**</span><span class="sxs-lookup"><span data-stu-id="a825d-258">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="a825d-259">**ELEMENT_TYPE_I8**</span><span class="sxs-lookup"><span data-stu-id="a825d-259">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="a825d-260">**ELEMENT_TYPE_U8**</span><span class="sxs-lookup"><span data-stu-id="a825d-260">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="a825d-261">**ELEMENT_TYPE_R4**</span><span class="sxs-lookup"><span data-stu-id="a825d-261">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="a825d-262">**ELEMENT_TYPE_R8**</span><span class="sxs-lookup"><span data-stu-id="a825d-262">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="a825d-263">**ELEMENT_TYPE_STRING**</span><span class="sxs-lookup"><span data-stu-id="a825d-263">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="a825d-264">**ELEMENT_TYPE_I**</span><span class="sxs-lookup"><span data-stu-id="a825d-264">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="a825d-265">**ELEMENT_TYPE_U**</span><span class="sxs-lookup"><span data-stu-id="a825d-265">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="a825d-266">Hay algunos tipos de valor del espacio de nombres **System** que se tratan de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="a825d-266">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="a825d-267">Dado que el código no administrado ya tiene formatos establecidos para estos tipos, la serialización tiene reglas especiales para serializarlos.</span><span class="sxs-lookup"><span data-stu-id="a825d-267">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="a825d-268">En la tabla siguiente se enumeran los tipos de valor especiales del espacio de nombres **System**, así como el tipo no administrado al que se serializan.</span><span class="sxs-lookup"><span data-stu-id="a825d-268">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="a825d-269">Tipo de valor System</span><span class="sxs-lookup"><span data-stu-id="a825d-269">System value type</span></span>|<span data-ttu-id="a825d-270">Tipo IDL</span><span class="sxs-lookup"><span data-stu-id="a825d-270">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="a825d-271">**DATE**</span><span class="sxs-lookup"><span data-stu-id="a825d-271">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="a825d-272">**DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="a825d-272">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="a825d-273">**GUID**</span><span class="sxs-lookup"><span data-stu-id="a825d-273">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="a825d-274">**OLE_COLOR**</span><span class="sxs-lookup"><span data-stu-id="a825d-274">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="a825d-275">El código siguiente muestra la definición de los tipos no administrados **DATE**, **GUID**, **DECIMAL** y **OLE_COLOR** de la biblioteca de tipos Stdole2.</span><span class="sxs-lookup"><span data-stu-id="a825d-275">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="a825d-276">Representación de biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="a825d-276">Type library representation</span></span>  
  
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
  
 <span data-ttu-id="a825d-277">El código siguiente muestra las definiciones correspondientes en la interfaz `IValueTypes` administrada.</span><span class="sxs-lookup"><span data-stu-id="a825d-277">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
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
  
#### <a name="type-library-representation"></a><span data-ttu-id="a825d-278">Representación de biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="a825d-278">Type library representation</span></span>  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="a825d-279">Vea también</span><span class="sxs-lookup"><span data-stu-id="a825d-279">See also</span></span>

- [<span data-ttu-id="a825d-280">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="a825d-280">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- [<span data-ttu-id="a825d-281">Copiar y fijar</span><span class="sxs-lookup"><span data-stu-id="a825d-281">Copying and Pinning</span></span>](copying-and-pinning.md)
- [<span data-ttu-id="a825d-282">Serialización predeterminada para matrices</span><span class="sxs-lookup"><span data-stu-id="a825d-282">Default Marshaling for Arrays</span></span>](default-marshaling-for-arrays.md)
- [<span data-ttu-id="a825d-283">Serialización predeterminada para objetos</span><span class="sxs-lookup"><span data-stu-id="a825d-283">Default Marshaling for Objects</span></span>](default-marshaling-for-objects.md)
- [<span data-ttu-id="a825d-284">Serialización predeterminada para cadenas</span><span class="sxs-lookup"><span data-stu-id="a825d-284">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
