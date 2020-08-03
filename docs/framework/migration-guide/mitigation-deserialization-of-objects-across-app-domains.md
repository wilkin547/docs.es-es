---
title: 'Mitigación: Deserialización de objetos en distintos dominios de aplicación'
description: Aprenda a diagnosticar y mitigar un problema en el que un intento de deserializar objetos en el contexto de una llamada lógica entre dominios de aplicación produce una excepción.
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: 20ea0f2f0b49000b7d1993adb583a803d9f5be6c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475247"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a><span data-ttu-id="d0cd7-103">Mitigación: deserialización de objetos en distintos dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d0cd7-103">Mitigation: Deserialization of Objects Across App Domains</span></span>
<span data-ttu-id="d0cd7-104">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-104">In some cases, when an app uses two or more app domains with different application bases, the attempt to deserialize objects in the logical call context across app domains throws an exception.</span></span>  
  
## <a name="diagnosing-the-issue"></a><span data-ttu-id="d0cd7-105">Diagnóstico del problema</span><span class="sxs-lookup"><span data-stu-id="d0cd7-105">Diagnosing the issue</span></span>  
 <span data-ttu-id="d0cd7-106">El problema se produce bajo la secuencia siguiente de condiciones:</span><span class="sxs-lookup"><span data-stu-id="d0cd7-106">The issue arises under the following sequence of conditions:</span></span>  
  
1. <span data-ttu-id="d0cd7-107">Una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-107">An app uses two or more app domains with different application bases.</span></span>  
  
2. <span data-ttu-id="d0cd7-108">Algunos tipos se agregan explícitamente a la clase <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> llamando a métodos como <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> o <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-108">Some types are explicitly added to the <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> by calling a method such as <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> or <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d0cd7-109">Estos tipos no están marcados como serializables y no se almacenan en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-109">These types are not marked as serializable and are not stored in the global assembly cache.</span></span>  
  
3. <span data-ttu-id="d0cd7-110">Después, el código que se ejecuta en el dominio de aplicación no predeterminado intenta leer un valor de un archivo de configuración o usar XML para deserializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-110">Later, code running in the non-default app domain tries to read a value from a configuration file or use XML to deserialize an object.</span></span>  
  
4. <span data-ttu-id="d0cd7-111">Para leer de un archivo de configuración o deserializar el objeto, un objeto <xref:System.Xml.XmlReader> intenta tener acceso al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-111">In order to read from a configuration file or deserialize the object, an <xref:System.Xml.XmlReader> object tries to access the configuration system.</span></span>  
  
5. <span data-ttu-id="d0cd7-112">Si aún no se ha inicializado el sistema de configuración, deberá completarse dicha inicialización.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-112">If the configuration system has not already been initialized, it must complete its initialization.</span></span> <span data-ttu-id="d0cd7-113">Esto significa, entre otras cosas, que el runtime tiene que crear una ruta de acceso estable para un sistema de configuración, lo que hace de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0cd7-113">This means, among other things, that the runtime has to create a stable path for a configuration system, which it does as follows:</span></span>  
  
    1. <span data-ttu-id="d0cd7-114">Busca evidencia para el dominio de aplicación no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-114">It looks for evidence for the non-default app domain.</span></span>  
  
    2. <span data-ttu-id="d0cd7-115">Intenta calcular la evidencia para el dominio de aplicación no predeterminado basándose en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-115">It tries to calculate the evidence for the non-default app domain based on the default app domain.</span></span>  
  
    3. <span data-ttu-id="d0cd7-116">La llamada para obtener evidencia del dominio de aplicación predeterminado desencadena una llamada de dominio de aplicación cruzado desde el dominio de aplicación no predeterminado al dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-116">The call to get evidence for the default app domain triggers a cross-app domain call from the non-default app domain to the default app domain.</span></span>  
  
    4. <span data-ttu-id="d0cd7-117">Como parte del contrato de dominio de aplicación cruzado de .NET Framework, el contenido del contexto de llamada lógico también tiene que calcularse en los límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-117">As part of the cross-app domain contract in the .NET Framework, the contents of the logical call context also have to be marshaled across app domain boundaries.</span></span>  
  
6. <span data-ttu-id="d0cd7-118">Dado que los tipos incluidos en el contexto de llamada lógico no se pueden resolver en el dominio de aplicación predeterminado, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-118">Because the types that are in the logical call context cannot be resolved in the default app domain, an exception is thrown.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d0cd7-119">Mitigación</span><span class="sxs-lookup"><span data-stu-id="d0cd7-119">Mitigation</span></span>  
 <span data-ttu-id="d0cd7-120">Para solucionar este problema, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="d0cd7-120">To work around this issue, do the following</span></span>  
  
1. <span data-ttu-id="d0cd7-121">Busque la llamada a `get_Evidence` en la pila de llamadas cuando se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-121">Look for the call to `get_Evidence` in the call stack when the exception is thrown.</span></span> <span data-ttu-id="d0cd7-122">La excepción puede ser cualquiera de las existentes en un gran subconjunto de excepciones, incluidas <xref:System.IO.FileNotFoundException> y <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="d0cd7-122">The exception can be any of a large subset of exceptions, including <xref:System.IO.FileNotFoundException> and <xref:System.Runtime.Serialization.SerializationException>.</span></span>  
  
2. <span data-ttu-id="d0cd7-123">Identifique el lugar de la aplicación donde no se agrega ningún objeto al contexto de llamada lógico y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0cd7-123">Identify the place in the app where no objects are added to the logical call context and add the following code:</span></span>  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a><span data-ttu-id="d0cd7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0cd7-124">See also</span></span>

- [<span data-ttu-id="d0cd7-125">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d0cd7-125">Application compatibility</span></span>](application-compatibility.md)
