---
title: '@ServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f7a0b077fb50149ad60034607eec413e774ee6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="e124e-101">Asocia el generador usado para crear el host del servicio con el servicio que se va a hospedar y otros aspectos de programación necesarios para tener acceso o compilar el código de hospedaje proporcionado en el archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="e124e-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e124e-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e124e-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="e124e-103">Atributos</span><span class="sxs-lookup"><span data-stu-id="e124e-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="e124e-104">Servicio</span><span class="sxs-lookup"><span data-stu-id="e124e-104">Service</span></span>  
 <span data-ttu-id="e124e-105">El nombre del tipo de CLR del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="e124e-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="e124e-106">Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.</span><span class="sxs-lookup"><span data-stu-id="e124e-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="e124e-107">Factory</span><span class="sxs-lookup"><span data-stu-id="e124e-107">Factory</span></span>  
 <span data-ttu-id="e124e-108">El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio.</span><span class="sxs-lookup"><span data-stu-id="e124e-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="e124e-109">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="e124e-109">This attribute is optional.</span></span> <span data-ttu-id="e124e-110">Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e124e-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="e124e-111">Depurar</span><span class="sxs-lookup"><span data-stu-id="e124e-111">Debug</span></span>  
 <span data-ttu-id="e124e-112">Indica si el servicio de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] debe compilarse con símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="e124e-112">Indicates whether the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service should be compiled with debug symbols.</span></span> <span data-ttu-id="e124e-113">Es `true` si el servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] debe compilarse con símbolos de depuración; de lo contrario, es `false`.</span><span class="sxs-lookup"><span data-stu-id="e124e-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="e124e-114">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="e124e-114">Language</span></span>  
 <span data-ttu-id="e124e-115">Especifica el lenguaje usado al compilar todo el código en línea del archivo (.svc).</span><span class="sxs-lookup"><span data-stu-id="e124e-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="e124e-116">Los valores pueden representar cualquier lenguaje compatible con .NET, incluyendo C#, VB y JS, que hacen referencia a C#, Visual Basic .NET y JScript .NET, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e124e-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="e124e-117">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="e124e-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="e124e-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="e124e-118">CodeBehind</span></span>  
 <span data-ttu-id="e124e-119">Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa dicho servicio no reside en el mismo archivo, y no se ha compilado en un ensamblado ni se ha colocado en el directorio \Bin.</span><span class="sxs-lookup"><span data-stu-id="e124e-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e124e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e124e-120">Remarks</span></span>  
 <span data-ttu-id="e124e-121"><xref:System.ServiceModel.ServiceHost> usado para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e124e-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] programming model.</span></span> <span data-ttu-id="e124e-122">Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.</span><span class="sxs-lookup"><span data-stu-id="e124e-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="e124e-123">las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e124e-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e124e-124">Aunque es posible proporcionar su propio generador (uno que devuelva su host derivado) especificando el nombre del tipo CLR de la implementación del generador en el [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva.</span><span class="sxs-lookup"><span data-stu-id="e124e-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="e124e-125">Para utilizar el generador de host de servicio personalizado propio en lugar del generador de manera predeterminada, basta con que proporcione el nombre de tipo en la [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e124e-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="e124e-126">Mantenga las implementaciones del generador tan ligeras como sea posible.</span><span class="sxs-lookup"><span data-stu-id="e124e-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="e124e-127">Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.</span><span class="sxs-lookup"><span data-stu-id="e124e-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="e124e-128">Por ejemplo, para habilitar un punto de conexión con AJAX habilitado para `MyService`, especifique el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para el valor de la `Factory` atributo, en lugar del predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory>, en la [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e124e-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e124e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e124e-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e124e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e124e-130">See Also</span></span>  
 [<span data-ttu-id="e124e-131">Host de servicio personalizado</span><span class="sxs-lookup"><span data-stu-id="e124e-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
