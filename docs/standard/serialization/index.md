---
title: 'Serialización: .NET'
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053348"
---
# <a name="serialization-in-net"></a><span data-ttu-id="80ee3-102">Serialización en .NET</span><span class="sxs-lookup"><span data-stu-id="80ee3-102">Serialization in .NET</span></span>

<span data-ttu-id="80ee3-103">La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar.</span><span class="sxs-lookup"><span data-stu-id="80ee3-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="80ee3-104">El complemento de serialización es deserialización, que convierte una secuencia en un objeto.</span><span class="sxs-lookup"><span data-stu-id="80ee3-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="80ee3-105">Juntos, estos procesos permiten almacenar y transferir datos.</span><span class="sxs-lookup"><span data-stu-id="80ee3-105">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="80ee3-106">.NET incluye las siguientes tecnologías de serialización:</span><span class="sxs-lookup"><span data-stu-id="80ee3-106">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="80ee3-107">La [serialización binaria](binary-serialization.md) conserva la fidelidad de tipos, lo que resulta útil para conservar el estado de un objeto entre las distintas invocaciones de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="80ee3-107">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="80ee3-108">Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="80ee3-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="80ee3-109">Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc.</span><span class="sxs-lookup"><span data-stu-id="80ee3-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="80ee3-110">La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.</span><span class="sxs-lookup"><span data-stu-id="80ee3-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="80ee3-111">La [serialización XML y SOAP](xml-and-soap-serialization.md) solo serializa propiedades y campos públicos y no conserva la fidelidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="80ee3-111">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="80ee3-112">Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos.</span><span class="sxs-lookup"><span data-stu-id="80ee3-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="80ee3-113">Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web.</span><span class="sxs-lookup"><span data-stu-id="80ee3-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="80ee3-114">SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.</span><span class="sxs-lookup"><span data-stu-id="80ee3-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="80ee3-115">La [serialización de JSON](system-text-json-overview.md) solo serializa las propiedades públicas y no conserva la fidelidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="80ee3-115">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="80ee3-116">JSON es un estándar abierto que es una opción atractiva para compartir datos a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="80ee3-116">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="80ee3-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="80ee3-117">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="80ee3-118">Contiene clases que se pueden usar para serializar y deserializar objetos.</span><span class="sxs-lookup"><span data-stu-id="80ee3-118">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="80ee3-119">Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.</span><span class="sxs-lookup"><span data-stu-id="80ee3-119">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="80ee3-120">Contiene clases que se pueden usar para serializar objetos en documentos o secuencias de formato JSON.</span><span class="sxs-lookup"><span data-stu-id="80ee3-120">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
