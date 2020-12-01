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
ms.openlocfilehash: b6a675bbbfb974d78539d02b31b500b03a2ac8f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256668"
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="76839-104">Cálculo de referencias predeterminado para matrices</span><span class="sxs-lookup"><span data-stu-id="76839-104">Default Marshaling for Arrays</span></span>

<span data-ttu-id="76839-105">En una aplicación que consta únicamente de código administrado, Common Language Runtime pasa los tipos de matriz como parámetros In/Out.</span><span class="sxs-lookup"><span data-stu-id="76839-105">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="76839-106">En cambio, el serializador de interoperabilidad pasa una matriz como parámetros In de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="76839-106">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="76839-107">Con [optimización de anclaje](copying-and-pinning.md), una matriz que puede transferirse en bloque de bits puede parecer que opera como un parámetro In/Out al interactuar con objetos en el mismo contenedor.</span><span class="sxs-lookup"><span data-stu-id="76839-107">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="76839-108">Pero si posteriormente se exporta el código a una biblioteca de tipos que se usa para generar el proxy entre equipos y esa biblioteca se usa para serializar las llamadas entre contenedores, las llamadas pueden revertir al comportamiento real del parámetro.</span><span class="sxs-lookup"><span data-stu-id="76839-108">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="76839-109">Las matrices son complejas por naturaleza y las distinciones entre matrices administradas y no administradas garantizan más información que otros tipos que no pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="76839-109">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span>  
  
## <a name="managed-arrays"></a><span data-ttu-id="76839-110">Matrices administradas</span><span class="sxs-lookup"><span data-stu-id="76839-110">Managed Arrays</span></span>  

 <span data-ttu-id="76839-111">Los tipos de matriz administrados pueden variar, pero la clase <xref:System.Array?displayProperty=nameWithType> es la clase base de todos los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-111">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="76839-112">La clase **System.Array** tiene propiedades para determinar el rango, la longitud y los límites inferior y superior de una matriz, así como métodos para tener acceso, ordenar, buscar, copiar y crear matrices.</span><span class="sxs-lookup"><span data-stu-id="76839-112">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="76839-113">Estos tipos de matriz son dinámicos y no tienen un tipo estático correspondiente definido en la biblioteca de clases base.</span><span class="sxs-lookup"><span data-stu-id="76839-113">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="76839-114">Es conveniente pensar en cada combinación de tipo de elemento y rango como en un tipo de matriz distinto.</span><span class="sxs-lookup"><span data-stu-id="76839-114">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="76839-115">Por tanto, una matriz unidimensional de enteros es de un tipo diferente que una matriz unidimensional de tipos dobles.</span><span class="sxs-lookup"><span data-stu-id="76839-115">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="76839-116">De forma similar, una matriz bidimensional de enteros es diferente de una matriz unidimensional de enteros.</span><span class="sxs-lookup"><span data-stu-id="76839-116">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="76839-117">Los límites de la matriz no se tienen en cuenta al comparar los tipos.</span><span class="sxs-lookup"><span data-stu-id="76839-117">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="76839-118">Como se muestra en la tabla siguiente, cualquier instancia de una matriz administrada debe ser de un tipo de elemento, rango y límite inferior específico.</span><span class="sxs-lookup"><span data-stu-id="76839-118">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="76839-119">Tipo de matriz administrada</span><span class="sxs-lookup"><span data-stu-id="76839-119">Managed array type</span></span>|<span data-ttu-id="76839-120">Tipo de elemento</span><span class="sxs-lookup"><span data-stu-id="76839-120">Element type</span></span>|<span data-ttu-id="76839-121">Rango</span><span class="sxs-lookup"><span data-stu-id="76839-121">Rank</span></span>|<span data-ttu-id="76839-122">Límite inferior</span><span class="sxs-lookup"><span data-stu-id="76839-122">Lower bound</span></span>|<span data-ttu-id="76839-123">Notación de firma</span><span class="sxs-lookup"><span data-stu-id="76839-123">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="76839-124">**ELEMENT_TYPE_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="76839-124">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="76839-125">Especificado por el tipo.</span><span class="sxs-lookup"><span data-stu-id="76839-125">Specified by type.</span></span>|<span data-ttu-id="76839-126">Especificado por el rango.</span><span class="sxs-lookup"><span data-stu-id="76839-126">Specified by rank.</span></span>|<span data-ttu-id="76839-127">Especificado opcionalmente por los límites.</span><span class="sxs-lookup"><span data-stu-id="76839-127">Optionally specified by bounds.</span></span>|<span data-ttu-id="76839-128">*type* **[** *n*,*m* **]**</span><span class="sxs-lookup"><span data-stu-id="76839-128">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="76839-129">**ELEMENT_TYPE_CLASS**</span><span class="sxs-lookup"><span data-stu-id="76839-129">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="76839-130">Desconocido</span><span class="sxs-lookup"><span data-stu-id="76839-130">Unknown</span></span>|<span data-ttu-id="76839-131">Desconocido</span><span class="sxs-lookup"><span data-stu-id="76839-131">Unknown</span></span>|<span data-ttu-id="76839-132">Desconocido</span><span class="sxs-lookup"><span data-stu-id="76839-132">Unknown</span></span>|<span data-ttu-id="76839-133">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="76839-133">**System.Array**</span></span>|  
|<span data-ttu-id="76839-134">**ELEMENT_TYPE_SZARRAY**</span><span class="sxs-lookup"><span data-stu-id="76839-134">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="76839-135">Especificado por el tipo.</span><span class="sxs-lookup"><span data-stu-id="76839-135">Specified by type.</span></span>|<span data-ttu-id="76839-136">1</span><span class="sxs-lookup"><span data-stu-id="76839-136">1</span></span>|<span data-ttu-id="76839-137">0</span><span class="sxs-lookup"><span data-stu-id="76839-137">0</span></span>|<span data-ttu-id="76839-138">*type* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="76839-138">*type* **[** *n* **]**</span></span>|  
  
## <a name="unmanaged-arrays"></a><span data-ttu-id="76839-139">Matrices no administradas</span><span class="sxs-lookup"><span data-stu-id="76839-139">Unmanaged Arrays</span></span>  

 <span data-ttu-id="76839-140">Las matrices no administradas son matrices seguras de estilo COM o matrices de estilo C de longitud fija o variable.</span><span class="sxs-lookup"><span data-stu-id="76839-140">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="76839-141">Las matrices seguras se describen a sí mismas y contienen el tipo, rango y límites de los datos de la matriz asociada.</span><span class="sxs-lookup"><span data-stu-id="76839-141">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="76839-142">Las matrices de estilo C son matrices con tipo unidimensionales con un límite inferior fijo de 0.</span><span class="sxs-lookup"><span data-stu-id="76839-142">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="76839-143">El servicio de serialización proporciona compatibilidad limitada para ambos tipos de matrices.</span><span class="sxs-lookup"><span data-stu-id="76839-143">The marshaling service has limited support for both types of arrays.</span></span>  
  
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="76839-144">Pasar parámetros de matriz a código de .NET</span><span class="sxs-lookup"><span data-stu-id="76839-144">Passing Array Parameters to .NET Code</span></span>  

 <span data-ttu-id="76839-145">Las matrices de estilo C y las matrices seguras pueden pasarse a código de .NET desde código no administrado como una matriz segura o una matriz de estilo C.</span><span class="sxs-lookup"><span data-stu-id="76839-145">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="76839-146">En la tabla siguiente se muestra el valor de tipo no administrado y el tipo importado.</span><span class="sxs-lookup"><span data-stu-id="76839-146">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="76839-147">Tipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-147">Unmanaged type</span></span>|<span data-ttu-id="76839-148">Tipo importado</span><span class="sxs-lookup"><span data-stu-id="76839-148">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="76839-149">**SafeArray(** *Type* **)**</span><span class="sxs-lookup"><span data-stu-id="76839-149">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="76839-150">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="76839-150">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="76839-151">Rango = 1, límite inferior = 0.</span><span class="sxs-lookup"><span data-stu-id="76839-151">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="76839-152">El tamaño se conoce solo si se proporciona en la firma administrada.</span><span class="sxs-lookup"><span data-stu-id="76839-152">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="76839-153">Las matrices seguras que no son de rango = 1 o límite inferior = 0 no se pueden serializar como **SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="76839-153">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="76839-154">*Type*  **[]**</span><span class="sxs-lookup"><span data-stu-id="76839-154">*Type*  **[]**</span></span>|<span data-ttu-id="76839-155">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span><span class="sxs-lookup"><span data-stu-id="76839-155">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="76839-156">Rango = 1, límite inferior = 0.</span><span class="sxs-lookup"><span data-stu-id="76839-156">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="76839-157">El tamaño se conoce solo si se proporciona en la firma administrada.</span><span class="sxs-lookup"><span data-stu-id="76839-157">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="76839-158">Matrices seguras</span><span class="sxs-lookup"><span data-stu-id="76839-158">Safe Arrays</span></span>  

 <span data-ttu-id="76839-159">Cuando se importa una matriz segura desde una biblioteca de tipos a un ensamblado .NET, la matriz se convierte en una matriz unidimensional de un tipo conocido (como **int**).</span><span class="sxs-lookup"><span data-stu-id="76839-159">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="76839-160">Las mismas reglas de conversión de tipos que se aplican a los parámetros también se aplican a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-160">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="76839-161">Por ejemplo, una matriz segura de tipos **BSTR** se convierte en una matriz administrada de cadenas y una matriz segura de variantes se convierte en una matriz administrada de objetos.</span><span class="sxs-lookup"><span data-stu-id="76839-161">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="76839-162">El tipo de elemento **SAFEARRAY** se captura de la biblioteca de tipos y se guarda en el valor **SAFEARRAY** de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType>.</span><span class="sxs-lookup"><span data-stu-id="76839-162">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="76839-163">Como el rango y los límites de la matriz segura no pueden determinarse a partir de la biblioteca de tipos, el rango se considera igual a 1 y el límite inferior igual a 0.</span><span class="sxs-lookup"><span data-stu-id="76839-163">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="76839-164">El rango y los límites se deben definir en la firma administrada generada por [TlbImp.exe (Importador de la biblioteca de tipos)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="76839-164">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="76839-165">Si el rango pasado al método en tiempo de ejecución difiere, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="76839-165">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="76839-166">Si difiere el tipo de la matriz pasado en tiempo de ejecución, se inicia una excepción <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="76839-166">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="76839-167">En el ejemplo siguiente se muestran las matrices seguras en código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="76839-167">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="76839-168">**Firma no administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-168">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="76839-169">**Firma administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-169">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="76839-170">Las matrices multidimensionales, o matrices seguras con límite distinto de cero, se pueden serializar en código administrado si la firma del método generada por Tlbimp.exe se modifica para indicar un tipo de elemento de **ELEMENT_TYPE_ARRAY** en lugar de **ELEMENT_ TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="76839-170">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="76839-171">Como alternativa, se puede usar el modificador **/sysarray** con Tlbimp.exe para importar todas las matrices como objetos <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76839-171">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="76839-172">En casos en los que se sabe que la matriz que se pasa es multidimensional, se puede editar el código de lenguaje intermedio (MSIL) de Microsoft generado mediante Tlbimp.exe y después volver a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="76839-172">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="76839-173">Para más información sobre cómo modificar código MSIL, vea [Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="76839-173">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="76839-174">Matrices de estilo C</span><span class="sxs-lookup"><span data-stu-id="76839-174">C-Style Arrays</span></span>  

 <span data-ttu-id="76839-175">Cuando se importa una matriz de estilo C desde una biblioteca de tipos a un ensamblado. NET, la matriz se convierte en **ELEMENT_TYPE_SZARRAY**.</span><span class="sxs-lookup"><span data-stu-id="76839-175">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="76839-176">El tipo de elemento de matriz se determina a partir de la biblioteca de tipos y se conserva durante la importación.</span><span class="sxs-lookup"><span data-stu-id="76839-176">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="76839-177">Las mismas reglas de conversión que se aplican a los parámetros también se aplican a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-177">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="76839-178">Por ejemplo, una matriz de tipos **LPStr** se convierte en una matriz de tipos **String**.</span><span class="sxs-lookup"><span data-stu-id="76839-178">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="76839-179">Tlbimp.exe captura el tipo de elemento de matriz y aplica el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro.</span><span class="sxs-lookup"><span data-stu-id="76839-179">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="76839-180">El rango de matriz se considera igual a 1.</span><span class="sxs-lookup"><span data-stu-id="76839-180">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="76839-181">Si el rango es mayor que 1, la matriz se serializa como una matriz unidimensional en el orden de importancia de la columna.</span><span class="sxs-lookup"><span data-stu-id="76839-181">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="76839-182">El límite inferior es siempre igual a 0.</span><span class="sxs-lookup"><span data-stu-id="76839-182">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="76839-183">Las bibliotecas de tipos pueden contener matrices de longitud fija o variable.</span><span class="sxs-lookup"><span data-stu-id="76839-183">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="76839-184">Tlbimp.exe solo puede importar matrices de longitud fija desde bibliotecas de tipos porque las bibliotecas de tipos no tienen la información necesaria para serializar matrices de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="76839-184">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="76839-185">Con las matrices de longitud fija, el tamaño se importa desde la biblioteca de tipos y se captura en el atributo **MarshalAsAttribute** que se aplica al parámetro.</span><span class="sxs-lookup"><span data-stu-id="76839-185">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="76839-186">Debe definir manualmente las bibliotecas de tipos que contienen matrices de longitud variable, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="76839-186">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="76839-187">**Firma no administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-187">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="76839-188">**Firma administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-188">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="76839-189">Aunque puede aplicar los atributos **size_is** o **length_is** a una matriz en código fuente de lenguaje de definición de interfaz (IDL) para transmitir el tamaño a un cliente, el compilador del Lenguaje de definición de interfaz de Microsoft (MIDL) no transmite esa información a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="76839-189">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="76839-190">Sin conocer el tamaño, el servicio de serialización de interoperabilidad no puede serializar los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-190">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="76839-191">Por tanto, las matrices de longitud variable se importan como argumentos por referencia.</span><span class="sxs-lookup"><span data-stu-id="76839-191">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="76839-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-192">For example:</span></span>  
  
 <span data-ttu-id="76839-193">**Firma no administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-193">**Unmanaged signature**</span></span>  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="76839-194">**Firma administrada**</span><span class="sxs-lookup"><span data-stu-id="76839-194">**Managed signature**</span></span>  
  
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
  
 <span data-ttu-id="76839-195">Puede proporcionar al serializador el tamaño de la matriz si modifica el código de lenguaje intermedio de Microsoft (MSIL) generado mediante Tlbimp.exe y después lo vuelve a compilar.</span><span class="sxs-lookup"><span data-stu-id="76839-195">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="76839-196">Para más información sobre cómo modificar código MSIL, vea [Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="76839-196">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).</span></span> <span data-ttu-id="76839-197">Para indicar el número de elementos de la matriz, aplique el tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parámetro de matriz de la definición de método administrado de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="76839-197">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
- <span data-ttu-id="76839-198">Identifique otro parámetro que contenga el número de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-198">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="76839-199">Los parámetros se identifican por posición, empezando con el primer parámetro como el número 0.</span><span class="sxs-lookup"><span data-stu-id="76839-199">The parameters are identified by position, starting with the first parameter as number 0.</span></span>
  
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
  
- <span data-ttu-id="76839-200">Defina el tamaño de la matriz como una constante.</span><span class="sxs-lookup"><span data-stu-id="76839-200">Define the size of the array as a constant.</span></span> <span data-ttu-id="76839-201">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-201">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="76839-202">Al serializar matrices desde código no administrado a código administrado, el serializador comprueba el atributo **MarshalAsAttribute** asociado con el parámetro para determinar el tamaño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-202">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="76839-203">Si no se especifica el tamaño de la matriz, solo se serializa un elemento.</span><span class="sxs-lookup"><span data-stu-id="76839-203">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76839-204">El atributo **MarshalAsAttribute** no tiene ningún efecto sobre la serialización de matrices administradas en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="76839-204">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="76839-205">En esa dirección, el tamaño de la matriz se determina mediante examen.</span><span class="sxs-lookup"><span data-stu-id="76839-205">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="76839-206">No hay ninguna manera de serializar un subconjunto de una matriz administrada.</span><span class="sxs-lookup"><span data-stu-id="76839-206">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="76839-207">El serializador de interoperabilidad usa los métodos **CoTaskMemAlloc** y **CoTaskMemFree** para asignar y recuperar memoria.</span><span class="sxs-lookup"><span data-stu-id="76839-207">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="76839-208">La asignación de memoria realizada por el código no administrado también debe usar estos métodos.</span><span class="sxs-lookup"><span data-stu-id="76839-208">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
## <a name="passing-arrays-to-com"></a><span data-ttu-id="76839-209">Pasar matrices a COM</span><span class="sxs-lookup"><span data-stu-id="76839-209">Passing Arrays to COM</span></span>  

 <span data-ttu-id="76839-210">Todos los tipos de matriz administrados pueden pasarse a código no administrado desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="76839-210">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="76839-211">Según el tipo administrado y los atributos que se le apliquen, se puede obtener acceso a la matriz como una matriz segura o una matriz de estilo C, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="76839-211">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="76839-212">Tipo de matriz administrada</span><span class="sxs-lookup"><span data-stu-id="76839-212">Managed array type</span></span>|<span data-ttu-id="76839-213">Exportado como</span><span class="sxs-lookup"><span data-stu-id="76839-213">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="76839-214">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span><span class="sxs-lookup"><span data-stu-id="76839-214">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="76839-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="76839-215"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="76839-216">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="76839-216">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="76839-217">El tipo se proporciona en la firma.</span><span class="sxs-lookup"><span data-stu-id="76839-217">Type is provided in the signature.</span></span> <span data-ttu-id="76839-218">El rango siempre es 1, el límite inferior es siempre 0.</span><span class="sxs-lookup"><span data-stu-id="76839-218">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="76839-219">El tamaño siempre se conoce en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76839-219">Size is always known at run time.</span></span>|  
|<span data-ttu-id="76839-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]</span><span class="sxs-lookup"><span data-stu-id="76839-220">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="76839-221">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="76839-221">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="76839-222">**UnmanagedType.LPArray**</span><span class="sxs-lookup"><span data-stu-id="76839-222">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="76839-223">El tipo, el rango y los límites se proporcionan en la firma.</span><span class="sxs-lookup"><span data-stu-id="76839-223">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="76839-224">El tamaño siempre se conoce en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76839-224">Size is always known at run time.</span></span>|  
|<span data-ttu-id="76839-225">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>\*\*</span><span class="sxs-lookup"><span data-stu-id="76839-225">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>\*\*</span></span>|<span data-ttu-id="76839-226">**UT_Interface**</span><span class="sxs-lookup"><span data-stu-id="76839-226">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="76839-227">**UnmanagedType.SafeArray(** *type* **)**</span><span class="sxs-lookup"><span data-stu-id="76839-227">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="76839-228">El tipo, el rango, los límites y el tamaño siempre se conocen en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76839-228">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="76839-229">Hay una limitación en la automatización OLE relacionada con las matrices de estructuras que contienen LPSTR o LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="76839-229">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="76839-230">Por tanto, los campos **String** tienen que serializarse como **UnmanagedType.BSTR**.</span><span class="sxs-lookup"><span data-stu-id="76839-230">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="76839-231">De lo contrario, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="76839-231">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="element_type_szarray"></a><span data-ttu-id="76839-232">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="76839-232">ELEMENT_TYPE_SZARRAY</span></span>  

 <span data-ttu-id="76839-233">Cuando un método que contiene un parámetro **ELEMENT_TYPE_SZARRAY** (matriz unidimensional) se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una **SAFEARRAY** de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="76839-233">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="76839-234">Las mismas reglas de conversión se aplican a los tipos de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="76839-234">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="76839-235">El contenido de la matriz administrada se copia automáticamente de la memoria administrada a **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="76839-235">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="76839-236">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-236">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-237">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-237">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="76839-238">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-238">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="76839-239">El rango de las matrices seguras siempre es 1 y el límite inferior siempre es 0.</span><span class="sxs-lookup"><span data-stu-id="76839-239">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="76839-240">El tamaño se determina en tiempo de ejecución por el tamaño de la matriz administrada que se pasa.</span><span class="sxs-lookup"><span data-stu-id="76839-240">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="76839-241">La matriz también se puede serializar como una matriz de estilo C mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="76839-241">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="76839-242">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-242">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-243">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-243">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="76839-244">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-244">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="76839-245">Aunque el serializador no tiene la información de longitud necesaria para serializar la matriz, la longitud de la matriz normalmente se pasa como argumento independiente para transmitir la longitud al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="76839-245">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="element_type_array"></a><span data-ttu-id="76839-246">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="76839-246">ELEMENT_TYPE_ARRAY</span></span>  

 <span data-ttu-id="76839-247">Cuando un método que contiene un parámetro **ELEMENT_TYPE_ARRAY** se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una **SAFEARRAY** de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="76839-247">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="76839-248">El contenido de la matriz administrada se copia automáticamente de la memoria administrada a **SAFEARRAY**.</span><span class="sxs-lookup"><span data-stu-id="76839-248">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="76839-249">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-249">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-250">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-250">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="76839-251">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-251">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="76839-252">El rango, el tamaño y los límites de las matrices seguras se determinan en tiempo de ejecución mediante las características de la matriz administrada.</span><span class="sxs-lookup"><span data-stu-id="76839-252">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="76839-253">La matriz también se puede serializar como una matriz de estilo C aplicando el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="76839-253">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="76839-254">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-254">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-255">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-255">Managed signature</span></span>  
  
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
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="76839-256">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-256">Unmanaged signature</span></span>  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="76839-257">Las matrices anidadas no se pueden serializar.</span><span class="sxs-lookup"><span data-stu-id="76839-257">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="76839-258">Por ejemplo, la siguiente firma genera un error cuando se exporta con el [exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="76839-258">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-259">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-259">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a><span data-ttu-id="76839-260">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="76839-260">ELEMENT_TYPE_CLASS \<System.Array></span></span>  

 <span data-ttu-id="76839-261">Cuando un método que contiene un parámetro <xref:System.Array?displayProperty=nameWithType> se exporta desde un ensamblado de .NET a una biblioteca de tipos, el parámetro de matriz se convierte en una interfaz **_Array**.</span><span class="sxs-lookup"><span data-stu-id="76839-261">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="76839-262">El contenido de la matriz administrada es accesible a través de los métodos y propiedades de la interfaz **_Array**.</span><span class="sxs-lookup"><span data-stu-id="76839-262">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="76839-263">**System.Array** también se puede serializar como una **SAFEARRAY** mediante el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="76839-263">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="76839-264">Cuando se serializa como una matriz segura, los elementos de matriz se calculan como variantes.</span><span class="sxs-lookup"><span data-stu-id="76839-264">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="76839-265">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76839-265">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="76839-266">Firma administrada</span><span class="sxs-lookup"><span data-stu-id="76839-266">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="76839-267">Prototipo no administrado</span><span class="sxs-lookup"><span data-stu-id="76839-267">Unmanaged signature</span></span>  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="76839-268">Matrices en estructuras</span><span class="sxs-lookup"><span data-stu-id="76839-268">Arrays within Structures</span></span>  

 <span data-ttu-id="76839-269">Las estructuras no administradas pueden contener matrices insertadas.</span><span class="sxs-lookup"><span data-stu-id="76839-269">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="76839-270">De forma predeterminada, estos campos de matriz insertados se calculan como SAFEARRAY.</span><span class="sxs-lookup"><span data-stu-id="76839-270">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="76839-271">En el ejemplo siguiente, `s1` es una matriz insertada que se asigna directamente desde la propia estructura.</span><span class="sxs-lookup"><span data-stu-id="76839-271">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="76839-272">Representación no administrada</span><span class="sxs-lookup"><span data-stu-id="76839-272">Unmanaged representation</span></span>  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="76839-273">Las matrices se pueden serializar como <xref:System.Runtime.InteropServices.UnmanagedType>, lo que requiere que establezca el campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="76839-273">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="76839-274">El tamaño solo se puede establecer como una constante.</span><span class="sxs-lookup"><span data-stu-id="76839-274">The size can be set only as a constant.</span></span> <span data-ttu-id="76839-275">En el código siguiente se muestra la definición administrada correspondiente de `MyStruct`.</span><span class="sxs-lookup"><span data-stu-id="76839-275">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76839-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="76839-276">See also</span></span>

- [<span data-ttu-id="76839-277">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="76839-277">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="76839-278">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="76839-278">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="76839-279">[Atributos direccionales](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="76839-279">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="76839-280">Copiar y fijar</span><span class="sxs-lookup"><span data-stu-id="76839-280">Copying and Pinning</span></span>](copying-and-pinning.md)
