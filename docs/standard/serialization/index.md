---
title: Serialización en .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 13ba804e76a64c6a0b32ba5a203258e76c209ff4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644915"
---
# <a name="serialization-in-net"></a><span data-ttu-id="81d8c-102">Serialización en .NET</span><span class="sxs-lookup"><span data-stu-id="81d8c-102">Serialization in .NET</span></span>
<span data-ttu-id="81d8c-103">La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar.</span><span class="sxs-lookup"><span data-stu-id="81d8c-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="81d8c-104">El complemento de serialización es deserialización, que convierte una secuencia en un objeto.</span><span class="sxs-lookup"><span data-stu-id="81d8c-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="81d8c-105">Juntos, estos procesos permiten almacenar los datos y transferirlos con facilidad.</span><span class="sxs-lookup"><span data-stu-id="81d8c-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="81d8c-106">.NET cuenta con dos tecnologías de serialización:</span><span class="sxs-lookup"><span data-stu-id="81d8c-106">.NET features two serialization technologies:</span></span>  
  
- <span data-ttu-id="81d8c-107">La serialización binaria conserva fidelidad de tipo, que es útil para conservar el estado de un objeto entre las invocaciones diferentes de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="81d8c-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="81d8c-108">Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="81d8c-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="81d8c-109">Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc.</span><span class="sxs-lookup"><span data-stu-id="81d8c-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="81d8c-110">La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.</span><span class="sxs-lookup"><span data-stu-id="81d8c-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="81d8c-111">La serialización XML serializa solo propiedades públicas y campos y no conserva la fidelidad de tipo.</span><span class="sxs-lookup"><span data-stu-id="81d8c-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="81d8c-112">Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos.</span><span class="sxs-lookup"><span data-stu-id="81d8c-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="81d8c-113">Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web.</span><span class="sxs-lookup"><span data-stu-id="81d8c-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="81d8c-114">SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.</span><span class="sxs-lookup"><span data-stu-id="81d8c-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81d8c-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="81d8c-115">In This Section</span></span>  
[<span data-ttu-id="81d8c-116">Temas "Cómo…" sobre serialización</span><span class="sxs-lookup"><span data-stu-id="81d8c-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="81d8c-117">Enumera vínculos a los temas "Cómo..." incluidos en esta sección.</span><span class="sxs-lookup"><span data-stu-id="81d8c-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="81d8c-118">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="81d8c-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="81d8c-119">Describe el mecanismo de la serialización binaria que está incluido con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="81d8c-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="81d8c-120">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="81d8c-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="81d8c-121">Describe el mecanismo de la serialización XML y SOAP que está incluido con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="81d8c-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="81d8c-122">Herramientas de serialización</span><span class="sxs-lookup"><span data-stu-id="81d8c-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="81d8c-123">Estas herramientas ayudan a desarrollar el código de serialización.</span><span class="sxs-lookup"><span data-stu-id="81d8c-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="81d8c-124">Ejemplos de serialización</span><span class="sxs-lookup"><span data-stu-id="81d8c-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="81d8c-125">En los ejemplos se muestra cómo hacer la serialización.</span><span class="sxs-lookup"><span data-stu-id="81d8c-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="81d8c-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="81d8c-126">Reference</span></span>
<span data-ttu-id="81d8c-127"><xref:System.Runtime.Serialization> Contiene clases que se pueden usar para serializar y deserializar objetos.</span><span class="sxs-lookup"><span data-stu-id="81d8c-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="81d8c-128">Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.</span><span class="sxs-lookup"><span data-stu-id="81d8c-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>