---
title: "Revisión de adaptabilidad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a><span data-ttu-id="97e55-102">Revisión de adaptabilidad</span><span class="sxs-lookup"><span data-stu-id="97e55-102">Localizability Review</span></span>
<span data-ttu-id="97e55-103">La revisión de localizabilidad es un paso intermedio en el desarrollo de una aplicación de uso internacional.</span><span class="sxs-lookup"><span data-stu-id="97e55-103">The localizability review is an intermediate step in the development of a world-ready application.</span></span> <span data-ttu-id="97e55-104">Comprueba que una aplicación globalizada está preparada para la localización e identifica cualquier código o los aspectos de la interfaz de usuario que requieren un tratamiento especial.</span><span class="sxs-lookup"><span data-stu-id="97e55-104">It verifies that a globalized application is ready for localization and identifies any code or any aspects of the user interface that require special handling.</span></span> <span data-ttu-id="97e55-105">Este paso también ayuda a asegurarse de que el proceso de localización no introducirá defectos funcionales en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="97e55-105">This step also helps ensure that the localization process will not introduce any functional defects into your application.</span></span> <span data-ttu-id="97e55-106">Cuando se han abordado todos los problemas provocados por la revisión de localizabilidad, la aplicación está preparada para la localización.</span><span class="sxs-lookup"><span data-stu-id="97e55-106">When all the issues raised by the localizability review have been addressed, your application is ready for localization.</span></span> <span data-ttu-id="97e55-107">Si la revisión de localizabilidad es exhaustiva, no debe tener que modificar cualquier código fuente durante el proceso de localización.</span><span class="sxs-lookup"><span data-stu-id="97e55-107">If the localizability review is thorough, you should not have to modify any source code during the localization process.</span></span>  
  
 <span data-ttu-id="97e55-108">La revisión de localizabilidad consta de las tres siguientes comprobaciones:</span><span class="sxs-lookup"><span data-stu-id="97e55-108">The localizability review consists of the following three checks:</span></span>  
  
-   [<span data-ttu-id="97e55-109">¿Se implementan las recomendaciones de globalización?</span><span class="sxs-lookup"><span data-stu-id="97e55-109">Are the globalization recommendations implemented?</span></span>](#global)  
  
-   [<span data-ttu-id="97e55-110">¿Se administran correctamente culturales características?</span><span class="sxs-lookup"><span data-stu-id="97e55-110">Are culture-sensitive features handled correctly?</span></span>](#culture)  
  
-   [<span data-ttu-id="97e55-111">¿Ha probado la aplicación con datos internacionales?</span><span class="sxs-lookup"><span data-stu-id="97e55-111">Have you tested your application with international data?</span></span>](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a><span data-ttu-id="97e55-112">Implementar recomendaciones de globalización</span><span class="sxs-lookup"><span data-stu-id="97e55-112">Implementing globalization recommendations</span></span>  
 <span data-ttu-id="97e55-113">Si ha diseñado y desarrollado su aplicación con la localización en mente, y si ha seguido las recomendaciones se describen en el [globalización](../../../docs/standard/globalization-localization/globalization.md) artículo, la revisión de localizabilidad en gran medida será un paso de aseguramiento de calidad .</span><span class="sxs-lookup"><span data-stu-id="97e55-113">If you have designed and developed your application with localization in mind, and if you have followed the recommendations discussed in the [Globalization](../../../docs/standard/globalization-localization/globalization.md) article, the localizability review will largely be a quality assurance pass.</span></span> <span data-ttu-id="97e55-114">De lo contrario, durante esta fase debe revisar e implementar las recomendaciones para [globalización](../../../docs/standard/globalization-localization/globalization.md)y corregir los errores en el código fuente que impiden la localización.</span><span class="sxs-lookup"><span data-stu-id="97e55-114">Otherwise, during this stage you should review and implement the recommendations for [globalization](../../../docs/standard/globalization-localization/globalization.md), and fix the errors in source code that prevent localization.</span></span>  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a><span data-ttu-id="97e55-115">Controlar características que tienen en cuenta la referencia cultural</span><span class="sxs-lookup"><span data-stu-id="97e55-115">Handling culture-sensitive features</span></span>  
 <span data-ttu-id="97e55-116">.NET Framework no proporciona soporte técnico de programación en un número de áreas que varían enormemente según la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="97e55-116">The .NET Framework does not provide programmatic support in a number of areas that vary widely by culture.</span></span> <span data-ttu-id="97e55-117">En la mayoría de los casos, tendrá que escribir código personalizado para controlar las áreas de características como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="97e55-117">In most cases, you have to write custom code to handle feature areas like the following:</span></span>  
  
-   <span data-ttu-id="97e55-118">Direcciones.</span><span class="sxs-lookup"><span data-stu-id="97e55-118">Addresses.</span></span>  
  
-   <span data-ttu-id="97e55-119">Números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="97e55-119">Telephone numbers.</span></span>  
  
-   <span data-ttu-id="97e55-120">Tamaños de papel.</span><span class="sxs-lookup"><span data-stu-id="97e55-120">Paper sizes.</span></span>  
  
-   <span data-ttu-id="97e55-121">Unidades de medida usada para las longitudes, pesos, área, volumen y temperaturas.</span><span class="sxs-lookup"><span data-stu-id="97e55-121">Units of measure used for lengths, weights, area, volume, and temperatures.</span></span> <span data-ttu-id="97e55-122">Aunque .NET Framework no ofrece compatibilidad integrada para la conversión entre unidades de medida, puede utilizar el <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> propiedad para determinar si un determinado país o región utiliza el sistema métrico, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="97e55-122">Although the .NET Framework does not offer built-in support for converting between units of measure, you can use the <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> property to determine whether a particular country or region uses the metric system, as the following example illustrates.</span></span>  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a><span data-ttu-id="97e55-123">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="97e55-123">Testing your application</span></span>  
 <span data-ttu-id="97e55-124">Para localizar la aplicación, debe probarla mediante el uso de datos internacionales en versiones internacionales del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="97e55-124">Before you localize your application, you should test it by using international data on international versions of the operating system.</span></span> <span data-ttu-id="97e55-125">Aunque la mayor parte de la interfaz de usuario no se traducirá en este momento, podrá detectar problemas como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="97e55-125">Although most of the user interface will not be localized at this point, you will be able to detect problems such as the following:</span></span>  
  
-   <span data-ttu-id="97e55-126">Datos serializados que deserializar correctamente en las versiones de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="97e55-126">Serialized data that does not deserialize correctly across operating system versions.</span></span>  
  
-   <span data-ttu-id="97e55-127">Datos numéricos que no reflejen las convenciones de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="97e55-127">Numeric data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="97e55-128">Por ejemplo, pueden mostrarse números con separadores de grupos inexacto, separadores decimales ni símbolos de moneda.</span><span class="sxs-lookup"><span data-stu-id="97e55-128">For example, numbers may be displayed with inaccurate group separators, decimal separators, or currency symbols.</span></span>  
  
-   <span data-ttu-id="97e55-129">Datos de fecha y hora que no reflejen las convenciones de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="97e55-129">Date and time data that does not reflect the conventions of the current culture.</span></span> <span data-ttu-id="97e55-130">Por ejemplo, los números que representan el mes y día pueden aparecer en el orden equivocado, separadores de fecha sea incorrectos o información de zona horaria puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="97e55-130">For example, numbers that represent the month and day may appear in the wrong order, date separators may be incorrect, or time zone information may be incorrect.</span></span>  
  
-   <span data-ttu-id="97e55-131">Recursos que no se puede encontrar porque no ha identificado una referencia cultural predeterminada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="97e55-131">Resources that cannot be found because you have not identified a default culture for your application.</span></span>  
  
-   <span data-ttu-id="97e55-132">Cadenas que se muestran en un orden inusual para la referencia cultural específica.</span><span class="sxs-lookup"><span data-stu-id="97e55-132">Strings that are displayed in an unusual order for the specific culture.</span></span>  
  
-   <span data-ttu-id="97e55-133">Cadena comparaciones o comparaciones de igualdad que devuelven resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="97e55-133">String comparisons or comparisons for equality that return unexpected results.</span></span>  
  
 <span data-ttu-id="97e55-134">Si ha seguido las recomendaciones de globalización al desarrollar la aplicación, controla correctamente, características de la cuenta de la referencia cultural e identificado y hace referencia a los problemas de localización que se produjeron durante las pruebas, puede continuar con el paso siguiente, [Localización](../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="97e55-134">If you've followed the globalization recommendations when developing your application, handled culture-sensitive features correctly, and identified and addressed the localization issues that arose during testing, you can proceed to the next step, [Localization](../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e55-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="97e55-135">See Also</span></span>  
 [<span data-ttu-id="97e55-136">Globalización y localización</span><span class="sxs-lookup"><span data-stu-id="97e55-136">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="97e55-137">Localización</span><span class="sxs-lookup"><span data-stu-id="97e55-137">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 [<span data-ttu-id="97e55-138">Globalización</span><span class="sxs-lookup"><span data-stu-id="97e55-138">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="97e55-139">Recursos de aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="97e55-139">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
