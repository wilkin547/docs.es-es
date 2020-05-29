---
title: Pasos del proceso de serialización
description: El proceso de serialización comienza cuando se llama al método Serialize en un formateador. En este artículo se describe la secuencia de eventos.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379099"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="08246-104">Pasos del proceso de serialización</span><span class="sxs-lookup"><span data-stu-id="08246-104">Steps in the serialization process</span></span>
<span data-ttu-id="08246-105">Cuando se llama al método <xref:System.Runtime.Serialization.Formatter.Serialize%2A> en un [formateador](xref:System.Runtime.Serialization.Formatter), la serialización de objetos procede según la secuencia siguiente de reglas:</span><span class="sxs-lookup"><span data-stu-id="08246-105">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="08246-106">Una comprobación se realiza para determinar si el formateador tiene un selector de suplente.</span><span class="sxs-lookup"><span data-stu-id="08246-106">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="08246-107">Si el formateador lo tiene, compruebe si el selector de suplente administra objetos del tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="08246-107">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="08246-108">Si el seleccionador administra el tipo de objeto, se llama a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> en el selector de suplente.</span><span class="sxs-lookup"><span data-stu-id="08246-108">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="08246-109">Si no hay ningún selector de suplente o si no administra el tipo de objeto, se realiza una comprobación para determinar si el objeto está marcado con el atributo [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="08246-109">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="08246-110">Si el objeto no está marcado, se genera <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="08246-110">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="08246-111">Si el objeto está marcado correctamente, compruebe si el objeto implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="08246-111">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="08246-112">Si es así, se llama a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> en el objeto.</span><span class="sxs-lookup"><span data-stu-id="08246-112">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="08246-113">Si el objeto no implementa <xref:System.Runtime.Serialization.ISerializable>, se usa la directiva de la serialización predeterminada, serializando todos los campos no marcados como [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="08246-113">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="08246-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="08246-114">See also</span></span>

- [<span data-ttu-id="08246-115">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="08246-115">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="08246-116">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="08246-116">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
