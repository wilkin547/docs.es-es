---
title: 'Mitigación: Deserialización de objetos en distintos dominios de aplicación'
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: e2d90a77cab699646bd31eaa162d1bd1744fd51b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457924"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a><span data-ttu-id="ef248-102">Mitigación: Deserialización de objetos en distintos dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="ef248-102">Mitigation: Deserialization of Objects Across App Domains</span></span>
<span data-ttu-id="ef248-103">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ef248-103">In some cases, when an app uses two or more app domains with different application bases, the attempt to deserialize objects in the logical call context across app domains throws an exception.</span></span>  
  
## <a name="diagnosing-the-issue"></a><span data-ttu-id="ef248-104">Diagnóstico del problema</span><span class="sxs-lookup"><span data-stu-id="ef248-104">Diagnosing the issue</span></span>  
 <span data-ttu-id="ef248-105">El problema se produce bajo la secuencia siguiente de condiciones:</span><span class="sxs-lookup"><span data-stu-id="ef248-105">The issue arises under the following sequence of conditions:</span></span>  
  
1. <span data-ttu-id="ef248-106">Una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef248-106">An app uses two or more app domains with different application bases.</span></span>  
  
2. <span data-ttu-id="ef248-107">Algunos tipos se agregan explícitamente a la clase <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> llamando a métodos como <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> o <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ef248-107">Some types are explicitly added to the <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> by calling a method such as <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> or <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ef248-108">Estos tipos no están marcados como serializables y no se almacenan en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ef248-108">These types are not marked as serializable and are not stored in the global assembly cache.</span></span>  
  
3. <span data-ttu-id="ef248-109">Después, el código que se ejecuta en el dominio de aplicación no predeterminado intenta leer un valor de un archivo de configuración o usar XML para deserializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="ef248-109">Later, code running in the non-default app domain tries to read a value from a configuration file or use XML to deserialize an object.</span></span>  
  
4. <span data-ttu-id="ef248-110">Para leer de un archivo de configuración o deserializar el objeto, un objeto <xref:System.Xml.XmlReader> intenta tener acceso al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="ef248-110">In order to read from a configuration file or deserialize the object, an <xref:System.Xml.XmlReader> object tries to access the configuration system.</span></span>  
  
5. <span data-ttu-id="ef248-111">Si aún no se ha inicializado el sistema de configuración, deberá completarse dicha inicialización.</span><span class="sxs-lookup"><span data-stu-id="ef248-111">If the configuration system has not already been initialized, it must complete its initialization.</span></span> <span data-ttu-id="ef248-112">Esto significa, entre otras cosas, que el runtime tiene que crear una ruta de acceso estable para un sistema de configuración, lo que hace de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef248-112">This means, among other things, that the runtime has to create a stable path for a configuration system, which it does as follows:</span></span>  
  
    1. <span data-ttu-id="ef248-113">Busca evidencia para el dominio de aplicación no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef248-113">It looks for evidence for the non-default app domain.</span></span>  
  
    2. <span data-ttu-id="ef248-114">Intenta calcular la evidencia para el dominio de aplicación no predeterminado basándose en el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef248-114">It tries to calculate the evidence for the non-default app domain based on the default app domain.</span></span>  
  
    3. <span data-ttu-id="ef248-115">La llamada para obtener evidencia del dominio de aplicación predeterminado desencadena una llamada de dominio de aplicación cruzado desde el dominio de aplicación no predeterminado al dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef248-115">The call to get evidence for the default app domain triggers a cross-app domain call from the non-default app domain to the default app domain.</span></span>  
  
    4. <span data-ttu-id="ef248-116">Como parte del contrato de dominio de aplicación cruzado de .NET Framework, el contenido del contexto de llamada lógico también tiene que calcularse en los límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef248-116">As part of the cross-app domain contract in the .NET Framework, the contents of the logical call context also have to be marshaled across app domain boundaries.</span></span>  
  
6. <span data-ttu-id="ef248-117">Dado que los tipos incluidos en el contexto de llamada lógico no se pueden resolver en el dominio de aplicación predeterminado, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ef248-117">Because the types that are in the logical call context cannot be resolved in the default app domain, an exception is thrown.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ef248-118">Mitigación</span><span class="sxs-lookup"><span data-stu-id="ef248-118">Mitigation</span></span>  
 <span data-ttu-id="ef248-119">Para solucionar este problema, haga lo siguiente</span><span class="sxs-lookup"><span data-stu-id="ef248-119">To work around this issue, do the following</span></span>  
  
1. <span data-ttu-id="ef248-120">Busque la llamada a `get_Evidence` en la pila de llamadas cuando se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="ef248-120">Look for the call to `get_Evidence` in the call stack when the exception is thrown.</span></span> <span data-ttu-id="ef248-121">La excepción puede ser cualquiera de las existentes en un gran subconjunto de excepciones, incluidas <xref:System.IO.FileNotFoundException> y <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="ef248-121">The exception can be any of a large subset of exceptions, including <xref:System.IO.FileNotFoundException> and <xref:System.Runtime.Serialization.SerializationException>.</span></span>  
  
2. <span data-ttu-id="ef248-122">Identifique el lugar de la aplicación donde no se agrega ningún objeto al contexto de llamada lógico y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef248-122">Identify the place in the app where no objects are added to the logical call context and add the following code:</span></span>  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a><span data-ttu-id="ef248-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef248-123">See also</span></span>

- [<span data-ttu-id="ef248-124">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ef248-124">Application compatibility</span></span>](application-compatibility.md)
