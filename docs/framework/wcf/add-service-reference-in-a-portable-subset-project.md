---
title: Agregar referencia de servicio en un proyecto de subconjuntos portátiles
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: e9a0d3fbc75a8c64af892f74acedfc41dc115da3
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687701"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="8f99d-102">Agregar referencia de servicio en un proyecto de subconjuntos portátiles</span><span class="sxs-lookup"><span data-stu-id="8f99d-102">Add Service Reference in a Portable Subset Project</span></span>

<span data-ttu-id="8f99d-103">Los proyectos de subconjuntos portátiles permiten a los programadores de ensamblados .NET mantener un único árbol de origen y un sistema de compilación, al mismo tiempo que se admiten varias implementaciones de .NET (escritorio, Silverlight, Windows Phone y Xbox).</span><span class="sxs-lookup"><span data-stu-id="8f99d-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and Xbox).</span></span> <span data-ttu-id="8f99d-104">Los proyectos de subconjuntos portátiles solo hacen referencia a bibliotecas portables que son ensamblados .NET que se pueden usar en cualquier implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="8f99d-104">Portable subset projects only reference portable libraries that are .NET assemblies that can be used on any .NET implementation.</span></span>
  
## <a name="add-service-reference-details"></a><span data-ttu-id="8f99d-105">Detalles de Agregar referencia de servicio</span><span class="sxs-lookup"><span data-stu-id="8f99d-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="8f99d-106">Al agregar una referencia de servicio a un proyecto de subconjunto portátil se aplican las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f99d-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1. <span data-ttu-id="8f99d-107">Para <xref:System.Xml.Serialization.XmlSerializer>, solo se permiten codificaciones literales.</span><span class="sxs-lookup"><span data-stu-id="8f99d-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="8f99d-108">Las codificaciones SOAP generan un error durante la importación.</span><span class="sxs-lookup"><span data-stu-id="8f99d-108">SOAP encodings generate an error during import.</span></span>  
  
2. <span data-ttu-id="8f99d-109">Para los servicios que usan escenarios <xref:System.Runtime.Serialization.DataContractSerializer>, se proporciona un suplente de contrato de datos para asegurarse de que los tipos reutilizados proceden únicamente del subconjunto portátil.</span><span class="sxs-lookup"><span data-stu-id="8f99d-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3. <span data-ttu-id="8f99d-110">Se omiten los extremos que confían en enlaces no admitidos en las bibliotecas portátiles (todos los enlaces excepto <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> sin flujo de transacción, sesiones confiables o codificación de MTOM y enlaces personalizados equivalentes).</span><span class="sxs-lookup"><span data-stu-id="8f99d-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4. <span data-ttu-id="8f99d-111">Los encabezados de mensaje se eliminan de todas las descripciones de mensaje en todas las operaciones antes de la importación.</span><span class="sxs-lookup"><span data-stu-id="8f99d-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5. <span data-ttu-id="8f99d-112">Los atributos no portátiles <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute> y <xref:System.ServiceModel.TransactionFlowAttribute> se quitan del código de proxy de cliente generado.</span><span class="sxs-lookup"><span data-stu-id="8f99d-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6. <span data-ttu-id="8f99d-113">Las propiedades no portátiles ProtectionLevel, SessionMode, IsInitiating e IsTerminating se quitan de <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute> y <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8f99d-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7. <span data-ttu-id="8f99d-114">Todas las operaciones de servicio se generan como operaciones asincrónicas en el proxy de cliente.</span><span class="sxs-lookup"><span data-stu-id="8f99d-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8. <span data-ttu-id="8f99d-115">Se quitan los constructores de cliente generados que usan tipos no portátiles.</span><span class="sxs-lookup"><span data-stu-id="8f99d-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="8f99d-116">Se expone una instancia de <xref:System.Net.CookieContainer> en el cliente generado.</span><span class="sxs-lookup"><span data-stu-id="8f99d-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="8f99d-117">Se inserta un comentario en la parte superior del archivo que identifica el ensamblado y la versión del generador de código:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span><span class="sxs-lookup"><span data-stu-id="8f99d-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span></span>  
  
11. <span data-ttu-id="8f99d-118">La interfaz <xref:System.Runtime.Serialization.ISerializable> no se admite.</span><span class="sxs-lookup"><span data-stu-id="8f99d-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="8f99d-119">Los enlaces Net.Tcp y PollingDuplex no se admiten</span><span class="sxs-lookup"><span data-stu-id="8f99d-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="8f99d-120"><xref:System.Runtime.Serialization.DataContractSerializer> se usará siempre para los errores.</span><span class="sxs-lookup"><span data-stu-id="8f99d-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <span data-ttu-id="8f99d-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> no se admite en proyectos de subconjuntos portátiles.</span><span class="sxs-lookup"><span data-stu-id="8f99d-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f99d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f99d-122">See also</span></span>

- [<span data-ttu-id="8f99d-123">Acceso a los servicios mediante un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="8f99d-123">Accessing Services Using a WCF Client</span></span>](accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="8f99d-124">Biblioteca de clases portable</span><span class="sxs-lookup"><span data-stu-id="8f99d-124">Portable Class Library</span></span>](../cross-platform/portable-class-library.md)
