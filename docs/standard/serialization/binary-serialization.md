---
title: Serialización binaria
description: En este artículo se describe la serialización binaria y los tipos para los que .NET Core la admite. Tenga en cuenta los peligros de la serialización binaria y sus alternativas.
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
ms.openlocfilehash: bfb504862232345db07bdc92993069fc87afdbeb
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282096"
---
# <a name="binary-serialization"></a><span data-ttu-id="98a17-104">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="98a17-104">Binary serialization</span></span>

<span data-ttu-id="98a17-105">La serialización se puede definir como el proceso de almacenar el estado de un objeto a los medios de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="98a17-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="98a17-106">Durante este proceso, los campos públicos y privados del objeto y el nombre de la clase, incluso el ensamblado que contiene la clase, se convierten en una secuencia de bytes, que se escribe a continuación en un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="98a17-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="98a17-107">Cuando se deserializa el objeto como consecuencia, se crea un clon exacto del objeto original.</span><span class="sxs-lookup"><span data-stu-id="98a17-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="98a17-108">Al implementar un mecanismo de la serialización en un entorno orientado a objetos, tiene que realizar varios intercambios entre la facilidad de uso y la flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="98a17-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="98a17-109">El proceso se puede automatizar en gran medida, con tal de que sea proporcionado el control suficiente sobre el proceso.</span><span class="sxs-lookup"><span data-stu-id="98a17-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="98a17-110">Por ejemplo, las situaciones se pueden presentar donde la serialización binaria simple no es suficiente, o podría haber una razón concreta para decidir qué campos en una clase necesitan ser serializados.</span><span class="sxs-lookup"><span data-stu-id="98a17-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="98a17-111">Las secciones siguientes examinan el sólido mecanismo de serialización proporcionado con .NET y resaltan varias características importantes que permiten personalizar el proceso para satisfacer las necesidades.</span><span class="sxs-lookup"><span data-stu-id="98a17-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="98a17-112">El estado de un objeto UTF-8 o UTF-7 codificado no se conserva si el objeto se serializa y se deserializa utilizando distintas versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="98a17-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="98a17-113">La serialización binaria permite modificar miembros privados dentro de un objeto y, por tanto, cambiar su estado.</span><span class="sxs-lookup"><span data-stu-id="98a17-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="98a17-114">Por este motivo, se recomiendan otros marcos de serialización, como <xref:System.Text.Json?displayProperty=fullName>, que operan en la superficie de la API pública.</span><span class="sxs-lookup"><span data-stu-id="98a17-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="98a17-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="98a17-115">.NET Core</span></span>

<span data-ttu-id="98a17-116">.NET Core admite la serialización binaria para un subconjunto de tipos.</span><span class="sxs-lookup"><span data-stu-id="98a17-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="98a17-117">Puede ver la lista de tipos compatibles en la sección [Tipos serializables](#serializable-types) siguiente.</span><span class="sxs-lookup"><span data-stu-id="98a17-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="98a17-118">Se garantiza que los tipos indicados son serializables entre .NET Framework 4.5.1 y versiones posteriores, y entre .NET Core 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="98a17-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="98a17-119">Otras implementaciones de .NET, como Mono, no son oficialmente compatibles, pero también deberían funcionar.</span><span class="sxs-lookup"><span data-stu-id="98a17-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="98a17-120">Tipos serializables</span><span class="sxs-lookup"><span data-stu-id="98a17-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="98a17-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="98a17-121">Type</span></span> | <span data-ttu-id="98a17-122">Notas</span><span class="sxs-lookup"><span data-stu-id="98a17-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="98a17-123">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="98a17-124">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-125">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="98a17-126">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-127">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-128">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="98a17-129">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="98a17-130">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="98a17-131">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="98a17-132">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="98a17-133">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="98a17-134">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="98a17-135">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-136">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-136">Starting in .NET Core 2.0.4.</span></span> |
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
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="98a17-137">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-138">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="98a17-139">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="98a17-140">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="98a17-141">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="98a17-142">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="98a17-143">No se admite la serialización desde .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98a17-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="98a17-144">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="98a17-145">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="98a17-146">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-147">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="98a17-148">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-149">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-150">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="98a17-151">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="98a17-152">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="98a17-153">A partir de .NET Core 2.0.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="98a17-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="98a17-154">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="98a17-155">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-156">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="98a17-157">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="98a17-158">Si establece `RemotingFormat` en `SerializationFormat.Binary`, solo se puede intercambiar con .NET Core 2.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="98a17-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="98a17-159">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="98a17-160">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="98a17-161">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="98a17-162">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="98a17-163">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-164">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-165">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-166">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="98a17-167">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-168">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-169">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="98a17-170">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="98a17-171">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="98a17-172">No se admite la serialización desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="98a17-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="98a17-173">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="98a17-174">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="98a17-175">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="98a17-176">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="98a17-177">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="98a17-178">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="98a17-179">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-180">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-181">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="98a17-182">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="98a17-183">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-184">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="98a17-185">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="98a17-186">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="98a17-187">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="98a17-188">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="98a17-189">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-190">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="98a17-191">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="98a17-192">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-193">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-194">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="98a17-195">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-196">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-197">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="98a17-198">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-199">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="98a17-200">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-201">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="98a17-202">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-203">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="98a17-204">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-205">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="98a17-206">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-207">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="98a17-208">A partir de .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="98a17-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="98a17-209">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="98a17-210">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="98a17-211">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-212">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="98a17-213">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-214">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="98a17-215">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="98a17-216">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="98a17-217">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-218">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="98a17-219">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="98a17-220">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="98a17-221">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="98a17-222">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="98a17-223">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="98a17-224">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="98a17-225">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="98a17-226">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="98a17-227">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-228">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="98a17-229">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="98a17-230">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="98a17-231">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="98a17-232">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="98a17-233">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="98a17-234">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="98a17-235">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-236">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="98a17-237">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="98a17-238">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="98a17-239">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="98a17-240">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="98a17-241">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-242">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="98a17-243">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-244">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="98a17-245">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="98a17-246">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="98a17-247">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="98a17-248">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-249">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-250">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="98a17-251">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-252">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="98a17-253">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="98a17-254">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="98a17-255">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-256">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="98a17-257">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="98a17-258">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="98a17-259">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="98a17-260">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="98a17-261">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="98a17-262">No se admite la serialización desde .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98a17-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="98a17-263">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-264">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="98a17-265">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="98a17-266">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-267">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-268">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="98a17-269">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="98a17-270">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="98a17-271">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="98a17-272">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="98a17-273">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="98a17-274">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="98a17-275">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="98a17-276">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="98a17-277">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-278">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="98a17-279">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-280">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="98a17-281">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="98a17-282">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-283">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="98a17-284">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-285">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="98a17-286">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-287">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="98a17-288">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="98a17-289">Datos de serialización limitados.</span><span class="sxs-lookup"><span data-stu-id="98a17-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-290">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="98a17-291">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="98a17-292">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="98a17-293">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="98a17-294">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="98a17-295">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="98a17-296">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="98a17-297">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="98a17-298">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="98a17-299">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-300">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="98a17-301">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="98a17-302">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="98a17-303">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="98a17-304">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="98a17-305">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-306">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="98a17-307">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="98a17-308">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-309">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="98a17-310">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="98a17-311">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-312">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-313">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="98a17-314">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-315">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="98a17-316">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="98a17-317">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-318">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="98a17-319">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="98a17-320">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="98a17-321">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="98a17-322">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="98a17-323">No es serializable en .NET Framework 4.7 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="98a17-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="98a17-324">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="98a17-325">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="98a17-326">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="98a17-327">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="98a17-328">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="98a17-329">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="98a17-330">A partir de .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="98a17-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="98a17-331">Vea también</span><span class="sxs-lookup"><span data-stu-id="98a17-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="98a17-332">Contiene clases que se pueden usar para serializar y deserializar objetos.</span><span class="sxs-lookup"><span data-stu-id="98a17-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="98a17-333">[Serialización SOAP y XML](xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="98a17-333">[XML and SOAP Serialization](xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="98a17-334">Describe el mecanismo de la serialización XML que está incluido con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="98a17-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="98a17-335">[Seguridad y serialización](../../framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="98a17-335">[Security and Serialization](../../framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="98a17-336">Describe las instrucciones de la codificación seguras que hay que seguir al escribir el código que realiza la serialización.</span><span class="sxs-lookup"><span data-stu-id="98a17-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="98a17-337">[Comunicación remota de .NET](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="98a17-337">[.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="98a17-338">Describe los diversos métodos en .NET Framework para las comunicaciones remotas.</span><span class="sxs-lookup"><span data-stu-id="98a17-338">Describes the various methods in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="98a17-339">[Servicios web XML creados con ASP.NET y clientes de servicio web XML](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="98a17-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="98a17-340">Artículos en los que se describe y explica cómo programar servicios web XML creados con ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="98a17-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
