---
title: Serialización binaria
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401272"
---
# <a name="binary-serialization"></a><span data-ttu-id="e9d79-102">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="e9d79-102">Binary serialization</span></span>

<span data-ttu-id="e9d79-103">La serialización se puede definir como el proceso de almacenar el estado de un objeto a los medios de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e9d79-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="e9d79-104">Durante este proceso, los campos públicos y privados del objeto y el nombre de la clase, incluso el ensamblado que contiene la clase, se convierten en una secuencia de bytes, que se escribe a continuación en un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="e9d79-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="e9d79-105">Cuando se deserializa el objeto como consecuencia, se crea un clon exacto del objeto original.</span><span class="sxs-lookup"><span data-stu-id="e9d79-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="e9d79-106">Al implementar un mecanismo de la serialización en un entorno orientado a objetos, tiene que realizar varios intercambios entre la facilidad de uso y la flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="e9d79-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="e9d79-107">El proceso se puede automatizar en gran medida, con tal de que sea proporcionado el control suficiente sobre el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9d79-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="e9d79-108">Por ejemplo, las situaciones se pueden presentar donde la serialización binaria simple no es suficiente, o podría haber una razón concreta para decidir qué campos en una clase necesitan ser serializados.</span><span class="sxs-lookup"><span data-stu-id="e9d79-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="e9d79-109">Las secciones siguientes examinan el sólido mecanismo de serialización proporcionado con .NET y resaltan varias características importantes que permiten personalizar el proceso para satisfacer las necesidades.</span><span class="sxs-lookup"><span data-stu-id="e9d79-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="e9d79-110">El estado de un objeto UTF-8 o UTF-7 codificado no se conserva si el objeto se serializa y se deserializa utilizando distintas versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9d79-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="e9d79-111">La serialización binaria permite modificar miembros privados dentro de un objeto y, por lo tanto, cambiar el estado del mismo.</span><span class="sxs-lookup"><span data-stu-id="e9d79-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="e9d79-112">Debido a esto, se recomiendan otros marcos de serialización, como <xref:System.Text.Json?displayProperty=fullName>, que funcionan en la superficie de API pública.</span><span class="sxs-lookup"><span data-stu-id="e9d79-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="e9d79-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="e9d79-113">.NET Core</span></span>

<span data-ttu-id="e9d79-114">.NET Core admite la serialización binaria para un subconjunto de tipos.</span><span class="sxs-lookup"><span data-stu-id="e9d79-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="e9d79-115">Puede ver la lista de tipos admitidos en la sección [Tipos serializables](#serializable-types) que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="e9d79-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="e9d79-116">Se garantiza que los tipos enumerados son serializables entre .NET Framework 4.5.1 y versiones posteriores y entre .NET Core 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9d79-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="e9d79-117">Otras implementaciones de .NET, como Mono, no se admiten oficialmente, pero también deben funcionar.</span><span class="sxs-lookup"><span data-stu-id="e9d79-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="e9d79-118">Tipos serializables</span><span class="sxs-lookup"><span data-stu-id="e9d79-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="e9d79-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9d79-119">Type</span></span> | <span data-ttu-id="e9d79-120">Notas</span><span class="sxs-lookup"><span data-stu-id="e9d79-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-121">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-122">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-123">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-124">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-125">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-126">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-127">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-128">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-129">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-130">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-131">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-132">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-133">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-134">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="e9d79-135">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-136">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-137">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-138">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-139">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-140">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e9d79-141">No se admite la serialización de .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e9d79-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-142">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="e9d79-143">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-144">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-145">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-146">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-147">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-148">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-149">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-150">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="e9d79-151">A partir de .NET Core 2.0.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9d79-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-152">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-153">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-154">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-155">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="e9d79-156">Si establece `RemotingFormat` `SerializationFormat.Binary`en , solo se puede intercambiar con .NET Core 2.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9d79-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-157">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-158">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-159">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-160">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-161">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-162">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-163">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-164">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-165">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-166">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-167">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-168">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-169">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e9d79-170">No se admite la serialización de .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="e9d79-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-171">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-172">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-173">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-174">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-175">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-176">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-177">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-178">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-179">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="e9d79-180">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-181">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-182">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-183">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-184">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-185">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-186">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-187">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-188">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-189">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-190">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-191">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-192">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-193">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-194">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-195">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-196">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-197">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-198">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-199">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-200">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-201">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-202">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-203">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-204">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-205">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="e9d79-206">A partir de .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="e9d79-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-207">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-208">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-209">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-210">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="e9d79-211">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-212">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-213">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-214">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-215">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-216">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-217">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-218">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-219">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-220">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-221">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-222">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-223">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-224">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-225">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-226">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-227">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-228">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-229">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-230">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-231">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-232">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-233">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-234">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-235">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-236">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-237">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-238">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-239">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-240">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-241">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-242">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-243">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-244">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-245">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-246">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-247">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-248">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-249">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-250">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-251">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-252">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-253">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-254">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-255">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-256">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-257">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-258">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-259">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e9d79-260">No se admite la serialización de .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e9d79-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-261">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-262">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-263">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-264">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-265">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-266">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-267">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-268">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-269">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-270">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-271">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-272">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-273">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-274">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-275">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-276">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-277">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-278">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-279">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-280">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-281">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="e9d79-282">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-283">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-284">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-285">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-286">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="e9d79-287">Datos de serialización limitados.</span><span class="sxs-lookup"><span data-stu-id="e9d79-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-288">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-289">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-290">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-291">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-292">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-293">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-294">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-295">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-296">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-297">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-298">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-299">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-300">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-301">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-302">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-303">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-304">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-305">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-306">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-307">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-308">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-309">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-310">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-311">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-312">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-313">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-314">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-315">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-316">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-317">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-318">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-319">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-320">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="e9d79-321">No se puede serializar en .NET Framework 4.7 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e9d79-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-322">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-323">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-324">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-325">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-326">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-327">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="e9d79-328">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="e9d79-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e9d79-329">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9d79-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="e9d79-330">Contiene clases que se pueden usar para serializar y deserializar objetos.</span><span class="sxs-lookup"><span data-stu-id="e9d79-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="e9d79-331">[Serialización XML y SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="e9d79-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="e9d79-332">Describe el mecanismo de la serialización XML que está incluido con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e9d79-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="e9d79-333">[Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="e9d79-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="e9d79-334">Describe las instrucciones de la codificación seguras que hay que seguir al escribir el código que realiza la serialización.</span><span class="sxs-lookup"><span data-stu-id="e9d79-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="e9d79-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e9d79-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="e9d79-336">Describe los distintos métodos que comienzan en .NET Framework para las comunicaciones remotas.</span><span class="sxs-lookup"><span data-stu-id="e9d79-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="e9d79-337">[Servicios Web XML creados con ASP.NET y clientes de servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e9d79-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="e9d79-338">Artículos que describen y explican cómo programar servicios Web XML creados mediante ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e9d79-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
