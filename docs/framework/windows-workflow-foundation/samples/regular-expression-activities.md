---
title: Actividades de expresión normales
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43743169"
---
# <a name="regular-expression-activities"></a><span data-ttu-id="b6e54-102">Actividades de expresión normales</span><span class="sxs-lookup"><span data-stu-id="b6e54-102">Regular Expression Activities</span></span>
<span data-ttu-id="b6e54-103">En este ejemplo se muestra cómo crear un conjunto de actividades que exponen la funcionalidad de expresión regular del espacio de nombres <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="b6e54-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="b6e54-104">Estas actividades personalizadas se pueden usar en una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="b6e54-105">Para obtener más información sobre las expresiones regulares, vea [System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span><span class="sxs-lookup"><span data-stu-id="b6e54-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="b6e54-106">En la siguiente tabla se detallan las actividades personalizadas de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="b6e54-107">Actividad</span><span class="sxs-lookup"><span data-stu-id="b6e54-107">Activity</span></span>|<span data-ttu-id="b6e54-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6e54-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b6e54-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="b6e54-109">IsMatch</span></span>|<span data-ttu-id="b6e54-110">Especifica si la expresión regular encontró una coincidencia en la cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="b6e54-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="b6e54-111">Coincidencias</span><span class="sxs-lookup"><span data-stu-id="b6e54-111">Matches</span></span>|<span data-ttu-id="b6e54-112">Busca todas las apariciones de una expresión regular en una cadena de entrada y devuelve todas las coincidencias correctas.</span><span class="sxs-lookup"><span data-stu-id="b6e54-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="b6e54-113">Cambia</span><span class="sxs-lookup"><span data-stu-id="b6e54-113">Replace</span></span>|<span data-ttu-id="b6e54-114">Dentro de una cadena de entrada especificada, reemplaza cadenas que hacen coincidir un patrón de expresión regular con una cadena de reemplazo especificada.</span><span class="sxs-lookup"><span data-stu-id="b6e54-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="b6e54-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="b6e54-115">IsMatch</span></span>  
 <span data-ttu-id="b6e54-116">La actividad personalizada `IsMatch` devuelve `true` si la propiedad de cadena `Input` encuentra una coincidencia en la expresión regular especificada en la propiedad `Pattern`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="b6e54-117">La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6e54-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="b6e54-118">En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="b6e54-119">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-119">Property or Return Value</span></span>|<span data-ttu-id="b6e54-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6e54-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="b6e54-121">Pattern (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-121">Pattern (required)</span></span>|<span data-ttu-id="b6e54-122">La expresión regular con la que buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="b6e54-123">Input (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-123">Input (required)</span></span>|<span data-ttu-id="b6e54-124">La cadena de entrada que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-124">The input string to search.</span></span>|  
|<span data-ttu-id="b6e54-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="b6e54-125">RegexOptions</span></span>|<span data-ttu-id="b6e54-126">Combinación OR bit a bit de [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b6e54-126">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="b6e54-127">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-127">Return value</span></span>|<span data-ttu-id="b6e54-128">`true` si la entrada encuentra una coincidencia en el patrón proporcionado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="b6e54-129">En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="b6e54-130">Coincidencias</span><span class="sxs-lookup"><span data-stu-id="b6e54-130">Matches</span></span>  
 <span data-ttu-id="b6e54-131">La actividad personalizada `Matches` busca todas las apariciones de una expresión regular en una cadena de entrada y devuelve todas las coincidencias correctas.</span><span class="sxs-lookup"><span data-stu-id="b6e54-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="b6e54-132">La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.Matches%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6e54-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="b6e54-133">En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="b6e54-134">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-134">Property or Return Value</span></span>|<span data-ttu-id="b6e54-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6e54-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="b6e54-136">Pattern (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-136">Pattern (required)</span></span>|<span data-ttu-id="b6e54-137">La expresión regular con la que buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="b6e54-138">Input (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-138">Input (required)</span></span>|<span data-ttu-id="b6e54-139">La cadena de entrada que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-139">The input string to search.</span></span>|  
|<span data-ttu-id="b6e54-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="b6e54-140">RegexOptions</span></span>|<span data-ttu-id="b6e54-141">Combinación OR bit a bit de [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b6e54-141">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="b6e54-142">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-142">Return Value</span></span>|<span data-ttu-id="b6e54-143">Un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene la colección de coincidencias correctas.</span><span class="sxs-lookup"><span data-stu-id="b6e54-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="b6e54-144">En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `Matches`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="b6e54-145">Cambia</span><span class="sxs-lookup"><span data-stu-id="b6e54-145">Replace</span></span>  
 <span data-ttu-id="b6e54-146">La actividad personalizada `Replace` busca una cadena de entrada y reemplaza todas las cadenas que hacen coincidir una expresión regular especificada con una cadena.</span><span class="sxs-lookup"><span data-stu-id="b6e54-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="b6e54-147">La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.Replace%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6e54-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="b6e54-148">En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `Replace`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="b6e54-149">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-149">Property or Return Value</span></span>|<span data-ttu-id="b6e54-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6e54-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="b6e54-151">Pattern (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-151">Pattern (required)</span></span>|<span data-ttu-id="b6e54-152">La expresión regular con la que buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="b6e54-153">Input (necesario)</span><span class="sxs-lookup"><span data-stu-id="b6e54-153">Input (required)</span></span>|<span data-ttu-id="b6e54-154">La cadena de entrada que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-154">The input string to search.</span></span>|  
|<span data-ttu-id="b6e54-155">Replacement</span><span class="sxs-lookup"><span data-stu-id="b6e54-155">Replacement</span></span>|<span data-ttu-id="b6e54-156">La cadena de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="b6e54-157">Si se establece `Replacement`, se omite la propiedad `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="b6e54-158">Es necesario establecer la propiedad `Replacement` o `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="b6e54-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="b6e54-159">MatchEvaluator</span></span>|<span data-ttu-id="b6e54-160">Un método personalizado que examina cada coincidencia y devuelve la cadena coincidente original o una cadena de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="b6e54-161">Si se establece `Replacement`, se omite la propiedad `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="b6e54-162">Es necesario establecer la propiedad `Replacement` o `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="b6e54-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="b6e54-163">RegexOptions</span></span>|<span data-ttu-id="b6e54-164">Combinación OR bit a bit de [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b6e54-164">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="b6e54-165">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6e54-165">Return Value</span></span>|<span data-ttu-id="b6e54-166">Un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene la colección de coincidencias correctas.</span><span class="sxs-lookup"><span data-stu-id="b6e54-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="b6e54-167">En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `Replace`.</span><span class="sxs-lookup"><span data-stu-id="b6e54-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b6e54-168">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6e54-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="b6e54-169">Abra el archivo de solución RegexActivities.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e54-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b6e54-170">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="b6e54-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b6e54-171">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b6e54-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b6e54-172">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b6e54-173">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b6e54-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b6e54-174">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b6e54-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b6e54-175">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b6e54-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`