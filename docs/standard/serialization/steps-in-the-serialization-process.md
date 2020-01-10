---
title: Pasos del proceso de serialización
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: f30dd550437e6bc1030c79865bf2edd2c0efbfa9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741053"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="e2326-102">Pasos del proceso de serialización</span><span class="sxs-lookup"><span data-stu-id="e2326-102">Steps in the serialization process</span></span>
<span data-ttu-id="e2326-103">Cuando se llama al método <xref:System.Runtime.Serialization.Formatter.Serialize%2A> en un [formateador](xref:System.Runtime.Serialization.Formatter), la serialización de objetos procede según la secuencia siguiente de reglas:</span><span class="sxs-lookup"><span data-stu-id="e2326-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="e2326-104">Una comprobación se realiza para determinar si el formateador tiene un selector de suplente.</span><span class="sxs-lookup"><span data-stu-id="e2326-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="e2326-105">Si el formateador lo tiene, compruebe si el selector de suplente administra objetos del tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="e2326-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="e2326-106">Si el seleccionador administra el tipo de objeto, se llama a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> en el selector de suplente.</span><span class="sxs-lookup"><span data-stu-id="e2326-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="e2326-107">Si no hay ningún selector de suplente o si no administra el tipo de objeto, se realiza una comprobación para determinar si el objeto está marcado con el atributo [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="e2326-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="e2326-108">Si el objeto no está marcado, se genera <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="e2326-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="e2326-109">Si el objeto está marcado correctamente, compruebe si el objeto implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="e2326-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="e2326-110">Si es así, se llama a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> en el objeto.</span><span class="sxs-lookup"><span data-stu-id="e2326-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="e2326-111">Si el objeto no implementa <xref:System.Runtime.Serialization.ISerializable>, se usa la directiva de la serialización predeterminada, serializando todos los campos no marcados como [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="e2326-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="e2326-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2326-112">See also</span></span>

- [<span data-ttu-id="e2326-113">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="e2326-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="e2326-114">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="e2326-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
