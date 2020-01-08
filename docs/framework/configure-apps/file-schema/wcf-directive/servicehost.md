---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3c7da8d5a473b801da8c48d1cb1504b95cc6c769
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342131"
---
# <a name="servicehost"></a><span data-ttu-id="fd564-101">\@ServiceHost</span><span class="sxs-lookup"><span data-stu-id="fd564-101">\@ServiceHost</span></span>
<span data-ttu-id="fd564-102">Asocia el generador usado para crear el host del servicio con el servicio que se va a hospedar y otros aspectos de programación necesarios para tener acceso o compilar el código de hospedaje proporcionado en el archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="fd564-102">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd564-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd564-103">Syntax</span></span>  
  
```xml  
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```  
  
## <a name="attributes"></a><span data-ttu-id="fd564-104">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd564-104">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="fd564-105">Servicio</span><span class="sxs-lookup"><span data-stu-id="fd564-105">Service</span></span>  
 <span data-ttu-id="fd564-106">El nombre del tipo de CLR del servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="fd564-106">The CLR type name of the service hosted.</span></span> <span data-ttu-id="fd564-107">Esto debería ser un nombre completo de un tipo que implementa uno o varios contactos del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd564-107">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="fd564-108">Factory</span><span class="sxs-lookup"><span data-stu-id="fd564-108">Factory</span></span>  
 <span data-ttu-id="fd564-109">El nombre de tipo de CLR del generador de host de servicio usado para crear instancias del host del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd564-109">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="fd564-110">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="fd564-110">This attribute is optional.</span></span> <span data-ttu-id="fd564-111">Si no se especifica, se usa el valor predeterminado <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="fd564-111">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="fd564-112">Depuración</span><span class="sxs-lookup"><span data-stu-id="fd564-112">Debug</span></span>  
 <span data-ttu-id="fd564-113">Indica si el servicio Windows Communication Foundation (WCF) se debe compilar con símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="fd564-113">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="fd564-114">`true` si el servicio WCF se debe compilar con símbolos de depuración; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fd564-114">`true` if the WCF service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="fd564-115">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="fd564-115">Language</span></span>  
 <span data-ttu-id="fd564-116">Especifica el lenguaje usado al compilar todo el código en línea del archivo (.svc).</span><span class="sxs-lookup"><span data-stu-id="fd564-116">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="fd564-117">Los valores pueden representar any. Lenguaje compatible con NET, incluidos `C#`, `VB`y `JS`, que hacen referencia a C#, Visual Basic y JScript .net, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fd564-117">The values can represent any .NET-supported language, including `C#`, `VB`, and `JS`, which refer to C#, Visual Basic, and JScript .NET, respectively.</span></span> <span data-ttu-id="fd564-118">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="fd564-118">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="fd564-119">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="fd564-119">CodeBehind</span></span>  
 <span data-ttu-id="fd564-120">Especifica el archivo de código fuente que implementa el servicio Web XML, cuando la clase que implementa dicho servicio no reside en el mismo archivo, y no se ha compilado en un ensamblado ni se ha colocado en el directorio \Bin.</span><span class="sxs-lookup"><span data-stu-id="fd564-120">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd564-121">Notas</span><span class="sxs-lookup"><span data-stu-id="fd564-121">Remarks</span></span>  
 <span data-ttu-id="fd564-122">El <xref:System.ServiceModel.ServiceHost> que se usa para hospedar el servicio es un punto de extensibilidad dentro del modelo de programación de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fd564-122">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="fd564-123">Se usa un patrón del generador para crear <xref:System.ServiceModel.ServiceHost> porque es, potencialmente, un tipo polimórfico del que el entorno de hospedaje no debería crear instancias directamente.</span><span class="sxs-lookup"><span data-stu-id="fd564-123">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="fd564-124">las implementaciones predeterminadas usan <xref:System.ServiceModel.Activation.ServiceHostFactory> para crear una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="fd564-124">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="fd564-125">Sin embargo, puede proporcionar su propio generador (uno que devuelve el host derivado) especificando el nombre de tipo de CLR de la implementación del generador en la directiva [\@ServiceHost](servicehost.md) .</span><span class="sxs-lookup"><span data-stu-id="fd564-125">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [\@ServiceHost](servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="fd564-126">Para usar su propio generador de host de servicio personalizado en lugar del generador predeterminado, simplemente proporcione el nombre de tipo en la directiva [@ServiceHost](servicehost.md) como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="fd564-126">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="fd564-127">Mantenga las implementaciones del generador tan ligeras como sea posible.</span><span class="sxs-lookup"><span data-stu-id="fd564-127">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="fd564-128">Si tiene mucha lógica personalizada, su código es más reutilizable si coloca esa lógica dentro de su host en lugar de dentro del generador.</span><span class="sxs-lookup"><span data-stu-id="fd564-128">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="fd564-129">Por ejemplo, para habilitar un punto de conexión habilitado para AJAX para `MyService`, especifique el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para el valor del atributo `Factory`, en lugar del <xref:System.ServiceModel.Activation.ServiceHostFactory>predeterminado, en la directiva [@ServiceHost](servicehost.md) , tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fd564-129">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd564-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd564-130">Example</span></span>  
  
```xml  
<% @ServiceHost
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd564-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd564-131">See also</span></span>

- [<span data-ttu-id="fd564-132">Host de servicio personalizado</span><span class="sxs-lookup"><span data-stu-id="fd564-132">Custom Service Host</span></span>](../../../wcf/samples/custom-service-host.md)
