---
title: Tipos primitivos (F#)
description: 'Detectar los tipos primitivos fundamentales que se utilizan en el lenguaje F #.'
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f23d98b-551b-4fd2-9f4f-0fd7254288ed
ms.openlocfilehash: b493cdf7116d94f66940d03b86e584bcecbbb0f1
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="primitive-types"></a><span data-ttu-id="daf36-104">Tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="daf36-104">Primitive Types</span></span>

<span data-ttu-id="daf36-105">Este tema enumeran los tipos primitivos fundamentales que se utilizan en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="daf36-105">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="daf36-106">También se proporcionan los tipos de .NET correspondientes y los valores máximos y mínimos para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="daf36-106">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="daf36-107">Resumen de tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="daf36-107">Summary of Primitive Types</span></span>
<span data-ttu-id="daf36-108">En la tabla siguiente se resume las propiedades de los tipos primitivos de F #.</span><span class="sxs-lookup"><span data-stu-id="daf36-108">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="daf36-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="daf36-109">Type</span></span>|<span data-ttu-id="daf36-110">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="daf36-110">.NET type</span></span>|<span data-ttu-id="daf36-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="daf36-111">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="daf36-112">Los valores posibles son `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="daf36-112">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="daf36-113">Valores de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="daf36-113">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="daf36-114">Valores de -128 a 127.</span><span class="sxs-lookup"><span data-stu-id="daf36-114">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="daf36-115">Valores de -32768 a 32767.</span><span class="sxs-lookup"><span data-stu-id="daf36-115">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="daf36-116">Valores de 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="daf36-116">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="daf36-117">Valores de -2.147.483.648 a 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="daf36-117">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="daf36-118">Valores de 0 a 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="daf36-118">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="daf36-119">Valores de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="daf36-119">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="daf36-120">Valores de 0 a 18.446.744.073.709.551.615.</span><span class="sxs-lookup"><span data-stu-id="daf36-120">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="daf36-121">Un puntero nativo como un entero con signo.</span><span class="sxs-lookup"><span data-stu-id="daf36-121">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="daf36-122">Un puntero nativo como un entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="daf36-122">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="daf36-123">Valores de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="daf36-123">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="daf36-124">Texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="daf36-124">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="daf36-125">Tipo de datos que tiene al menos 28 dígitos significativos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="daf36-125">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="daf36-126">No aplicable</span><span class="sxs-lookup"><span data-stu-id="daf36-126">not applicable</span></span>|<span data-ttu-id="daf36-127">Indica la ausencia de un valor real.</span><span class="sxs-lookup"><span data-stu-id="daf36-127">Indicates the absence of an actual value.</span></span> <span data-ttu-id="daf36-128">El tipo tiene un único valor formal, que se indica `()`.</span><span class="sxs-lookup"><span data-stu-id="daf36-128">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="daf36-129">El valor de la unidad, `()`, a menudo se utiliza como un marcador de posición donde se necesita un valor pero ningún valor real está disponible o tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="daf36-129">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="daf36-130">No indica que ningún tipo o valor.</span><span class="sxs-lookup"><span data-stu-id="daf36-130">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="daf36-131">Tipo de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="daf36-131">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="daf36-132">Tipo de punto flotante de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="daf36-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="daf36-133">Puede realizar cálculos con enteros demasiado grandes para el tipo de entero de 64 bits mediante el [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo.</span><span class="sxs-lookup"><span data-stu-id="daf36-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="daf36-134">`bigint`no se considera un tipo primitivo; es una abreviatura de `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="daf36-134">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="daf36-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="daf36-135">See Also</span></span>
[<span data-ttu-id="daf36-136">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="daf36-136">F# Language Reference</span></span>](index.md)
