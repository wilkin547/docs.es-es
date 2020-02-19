---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 39dc92d65a41d223ebd39aec3dc59871ad1fd101
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448690"
---
# <a name="behaviorextensions"></a><span data-ttu-id="73143-101">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="73143-101">\<behaviorExtensions></span></span>
<span data-ttu-id="73143-102">Las extensiones de comportamiento le permiten al usuario crear los elementos de comportamiento definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="73143-102">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="73143-103">Estos elementos se pueden utilizar junto a los elementos de comportamiento de Windows Communication Foundation (WCF) estándares.</span><span class="sxs-lookup"><span data-stu-id="73143-103">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="73143-104">La sección `behaviorExtensions` define el elemento tal como se puede utilizar en configuración.</span><span class="sxs-lookup"><span data-stu-id="73143-104">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="73143-105">Éste es un ejemplo de una extensión de comportamiento típica.</span><span class="sxs-lookup"><span data-stu-id="73143-105">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="73143-106">Para agregar capacidades de configuración al elemento, necesita escribir y registrar un elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="73143-106">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="73143-107">Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="73143-107">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="73143-108">Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="73143-108">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a><span data-ttu-id="73143-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="73143-109">Security</span></span>  
 <span data-ttu-id="73143-110">Se recomienda fuertemente que utilice nombres de ensamblado completo al registrar los tipos en los archivos `machine.config` y `app.config`.</span><span class="sxs-lookup"><span data-stu-id="73143-110">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="73143-111">Si no se define el tipo singularmente, el cargador de tipo CLR lo busca en las ubicaciones siguientes en el orden especificado:</span><span class="sxs-lookup"><span data-stu-id="73143-111">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="73143-112">Si se conoce el ensamblado del tipo, el cargador busca en las ubicaciones de la redirección del archivo de configuración GAC, el ensamblado actual utilizando información de configuración, y el directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73143-112">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="73143-113">Si el ensamblado es desconocido, el cargador busca en el ensamblado actual, mscorlib y la ubicación devueltos por el controlador de eventos `TypeResolve`.</span><span class="sxs-lookup"><span data-stu-id="73143-113">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="73143-114">Este orden de búsqueda de CLR se puede modificar con enlaces como el mecanismo de Tipo Reenvío y el evento AppDomain.TypeResolve.</span><span class="sxs-lookup"><span data-stu-id="73143-114">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="73143-115">Un atacante se puede aprovechar del orden de búsqueda de CLR y ejecutar un código desautorizado.</span><span class="sxs-lookup"><span data-stu-id="73143-115">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="73143-116">Al utilizar nombres completos (seguros), se identifica exclusivamente a un tipo, lo que mejora la seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="73143-116">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="73143-117">Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md) y <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="73143-117">For more information, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73143-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73143-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="73143-119">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="73143-119">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
