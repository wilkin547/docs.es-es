---
title: '&lt;behaviorExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c520a8a06a593d8937ca840602ba5bcc7b2d44b4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="38454-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="38454-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="38454-103">Las extensiones de comportamiento le permiten al usuario crear los elementos de comportamiento definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="38454-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="38454-104">Estos elementos se pueden utilizar junto a los elementos de comportamiento de Windows Communication Foundation (WCF) estándares.</span><span class="sxs-lookup"><span data-stu-id="38454-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="38454-105">La sección `behaviorExtensions` define el elemento tal como se puede utilizar en configuración.</span><span class="sxs-lookup"><span data-stu-id="38454-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="38454-106">Éste es un ejemplo de una extensión de comportamiento típica.</span><span class="sxs-lookup"><span data-stu-id="38454-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="38454-107">Para agregar capacidades de configuración al elemento, necesita escribir y registrar un elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="38454-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="38454-108">Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="38454-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="38454-109">Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="38454-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="38454-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="38454-110">Security</span></span>  
 <span data-ttu-id="38454-111">Se recomienda fuertemente que utilice nombres de ensamblado completo al registrar los tipos en los archivos `machine.config` y `app.config`.</span><span class="sxs-lookup"><span data-stu-id="38454-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="38454-112">Si no se define el tipo singularmente, el cargador de tipo CLR lo busca en las ubicaciones siguientes en el orden especificado:</span><span class="sxs-lookup"><span data-stu-id="38454-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="38454-113">Si se conoce el ensamblado del tipo, el cargador busca en las ubicaciones de la redirección del archivo de configuración GAC, el ensamblado actual utilizando información de configuración, y el directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38454-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="38454-114">Si el ensamblado es desconocido, el cargador busca en el ensamblado actual, mscorlib y la ubicación devueltos por el controlador de eventos `TypeResolve`.</span><span class="sxs-lookup"><span data-stu-id="38454-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="38454-115">Este orden de búsqueda de CLR se puede modificar con enlaces como el mecanismo de Tipo Reenvío y el evento AppDomain.TypeResolve.</span><span class="sxs-lookup"><span data-stu-id="38454-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="38454-116">Un atacante se puede aprovechar del orden de búsqueda de CLR y ejecutar un código desautorizado.</span><span class="sxs-lookup"><span data-stu-id="38454-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="38454-117">Al utilizar los nombres completos (seguros) sólo se identifica un tipo y aumenta la seguridad de su sistema.</span><span class="sxs-lookup"><span data-stu-id="38454-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="38454-118">Para obtener más información, consulte [cómo el tiempo de ejecución ubica ensamblados](http://go.microsoft.com/fwlink/?LinkId=95336) y <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="38454-118">For more information, see [How the Runtime Locates Assemblies](http://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38454-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="38454-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="38454-120">Configurar y extender el tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="38454-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
