---
title: Tipos básicos
description: 'Descubra los tipos básicos fundamentales que se usan en el lenguaje F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 2bfc9ba9370cb8ba1fcc1d42369c2551cbb57623
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456918"
---
# <a name="basic-types"></a><span data-ttu-id="f308a-103">Tipos básicos</span><span class="sxs-lookup"><span data-stu-id="f308a-103">Basic types</span></span>

<span data-ttu-id="f308a-104">En este tema se enumeran los tipos básicos que se definen en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="f308a-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="f308a-105">Estos tipos son los más fundamentales en F #, que forman la base de casi todos los programas de F #.</span><span class="sxs-lookup"><span data-stu-id="f308a-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="f308a-106">Son un superconjunto de tipos primitivos de .NET.</span><span class="sxs-lookup"><span data-stu-id="f308a-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="f308a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f308a-107">Type</span></span>|<span data-ttu-id="f308a-108">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="f308a-108">.NET type</span></span>|<span data-ttu-id="f308a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f308a-109">Description</span></span>|<span data-ttu-id="f308a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f308a-110">Example</span></span>|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="f308a-111">Los valores posibles son `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="f308a-111">Possible values are `true` and `false`.</span></span>|`true`/`false`|
|`byte`|<xref:System.Byte>|<span data-ttu-id="f308a-112">Valores de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="f308a-112">Values from 0 to 255.</span></span>|`1uy`|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="f308a-113">Valores de-128 a 127.</span><span class="sxs-lookup"><span data-stu-id="f308a-113">Values from -128 to 127.</span></span>|`1y`|
|`int16`|<xref:System.Int16>|<span data-ttu-id="f308a-114">Valores de-32768 a 32767.</span><span class="sxs-lookup"><span data-stu-id="f308a-114">Values from -32768 to 32767.</span></span>|`1s`|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="f308a-115">Valores de 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="f308a-115">Values from 0 to 65535.</span></span>|`1us`|
|`int`|<xref:System.Int32>|<span data-ttu-id="f308a-116">Valores de-2.147.483.648 a 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="f308a-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|`1`|
|`uint`|<xref:System.UInt32>|<span data-ttu-id="f308a-117">Valores de 0 a 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="f308a-117">Values from 0 to 4,294,967,295.</span></span>|`1u`|
|`int64`|<xref:System.Int64>|<span data-ttu-id="f308a-118">Valores de-9223372036854775808 a 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="f308a-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|`1L`|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="f308a-119">Valores de 0 a 18446744073709551615.</span><span class="sxs-lookup"><span data-stu-id="f308a-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|`1UL`|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="f308a-120">Puntero nativo como entero con signo.</span><span class="sxs-lookup"><span data-stu-id="f308a-120">A native pointer as a signed integer.</span></span>|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="f308a-121">Puntero nativo como entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="f308a-121">A native pointer as an unsigned integer.</span></span>|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="f308a-122">Un tipo de datos de punto flotante que tiene al menos 28 dígitos significativos.</span><span class="sxs-lookup"><span data-stu-id="f308a-122">A floating point data type that has at least 28 significant digits.</span></span>|`1.0`|
|<span data-ttu-id="f308a-123">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="f308a-123">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="f308a-124">Tipo de punto flotante de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f308a-124">A 64-bit floating point type.</span></span>|`1.0`|
|<span data-ttu-id="f308a-125">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="f308a-125">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="f308a-126">Tipo de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f308a-126">A 32-bit floating point type.</span></span>|`1.0f`|
|`char`|<xref:System.Char>|<span data-ttu-id="f308a-127">Valores de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="f308a-127">Unicode character values.</span></span>|`'c'`|
|`string`|<xref:System.String>|<span data-ttu-id="f308a-128">Texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="f308a-128">Unicode text.</span></span>|`"str"`|
|`unit`|<span data-ttu-id="f308a-129">no aplicable</span><span class="sxs-lookup"><span data-stu-id="f308a-129">not applicable</span></span>|<span data-ttu-id="f308a-130">Indica la ausencia de un valor real.</span><span class="sxs-lookup"><span data-stu-id="f308a-130">Indicates the absence of an actual value.</span></span> <span data-ttu-id="f308a-131">El tipo solo tiene un valor formal, que se indica `()` .</span><span class="sxs-lookup"><span data-stu-id="f308a-131">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="f308a-132">El valor de unidad, `()` , se usa a menudo como un marcador de posición en el que se necesita un valor, pero no hay ningún valor real disponible o tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="f308a-132">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|`()`|

> [!NOTE]
> <span data-ttu-id="f308a-133">Puede realizar cálculos con enteros demasiado grandes para el tipo entero de 64 bits mediante el `bigint` tipo.</span><span class="sxs-lookup"><span data-stu-id="f308a-133">You can perform computations with integers too big for the 64-bit integer type by using the `bigint` type.</span></span> <span data-ttu-id="f308a-134">`bigint` no se considera un tipo básico; es una abreviatura de `System.Numerics.BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="f308a-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f308a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f308a-135">See also</span></span>

- [<span data-ttu-id="f308a-136">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f308a-136">F# Language Reference</span></span>](index.md)
