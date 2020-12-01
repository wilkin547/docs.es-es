---
title: programar protocolos acoplables
description: Obtenga información sobre la compatibilidad de las clases abstractas WebRequest y WebResponse con protocolos conectables, que permiten a una aplicación obtener datos sin necesidad de especificar un protocolo.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: a3f8106b238c28de77362e73aa26667209f6b517
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263183"
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="2f009-103">programar protocolos acoplables</span><span class="sxs-lookup"><span data-stu-id="2f009-103">Programming Pluggable Protocols</span></span>

<span data-ttu-id="2f009-104">Las clases abstractas <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan la base para los protocolos conectables.</span><span class="sxs-lookup"><span data-stu-id="2f009-104">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="2f009-105">Al derivar clases específicas del protocolo de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>, una aplicación puede solicitar datos desde un recurso de Internet y leer la respuesta sin especificar el protocolo que se está usando.</span><span class="sxs-lookup"><span data-stu-id="2f009-105">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="2f009-106">Para poder crear una <xref:System.Net.WebRequest> específica del protocolo, debe registrar su método Create.</span><span class="sxs-lookup"><span data-stu-id="2f009-106">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="2f009-107">Use el método estático <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> de <xref:System.Net.WebRequest> para registrar una <xref:System.Net.WebRequest> descendiente para controlar un conjunto de solicitudes a un esquema concreto de Internet, a un servidor y un esquema, o a un esquema, servidor y ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="2f009-107">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="2f009-108">En la mayoría de los casos podrá enviar y recibir datos mediante los métodos y propiedades de la clase <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="2f009-108">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="2f009-109">Pero si necesita tener acceso a propiedades específicas del protocolo, puede convertir el tipo de una <xref:System.Net.WebRequest> a una instancia específica de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="2f009-109">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="2f009-110">Para aprovechar las ventajas de los protocolos conectables, los descendientes de <xref:System.Net.WebRequest> deben proporcionar una transacción predeterminada de solicitud y respuesta que no requiera establecer propiedades específicas del protocolo.</span><span class="sxs-lookup"><span data-stu-id="2f009-110">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="2f009-111">Por ejemplo, la clase <xref:System.Net.HttpWebRequest>, que implementa la clase <xref:System.Net.WebRequest> para HTTP, proporciona una solicitud `GET` de forma predeterminada y devuelve una <xref:System.Net.HttpWebResponse> que contiene la secuencia devuelta desde el servidor web.</span><span class="sxs-lookup"><span data-stu-id="2f009-111">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f009-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f009-112">See also</span></span>

- [<span data-ttu-id="2f009-113">Derivar de WebRequest</span><span class="sxs-lookup"><span data-stu-id="2f009-113">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
- [<span data-ttu-id="2f009-114">Derivar de WebResponse</span><span class="sxs-lookup"><span data-stu-id="2f009-114">Deriving from WebResponse</span></span>](deriving-from-webresponse.md)
- [<span data-ttu-id="2f009-115">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f009-115">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="2f009-116">Cómo: Convertir un elemento WebRequest a propiedades específicas del protocolo de acceso</span><span class="sxs-lookup"><span data-stu-id="2f009-116">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
