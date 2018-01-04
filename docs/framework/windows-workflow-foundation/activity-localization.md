---
title: "Adaptación de actividades"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccabcda9e26751db80ee7e955458d0eee0cae7e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="activity-localization"></a><span data-ttu-id="bacf2-102">Adaptación de actividades</span><span class="sxs-lookup"><span data-stu-id="bacf2-102">Activity Localization</span></span>
<span data-ttu-id="bacf2-103">Cuando las aplicaciones y componentes del flujo de trabajo tienen el potencial para que se adapten a otras referencias culturales e idiomas, las cadenas de recurso deben usarse de manera que se puedan adaptar sin recompilar.</span><span class="sxs-lookup"><span data-stu-id="bacf2-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="bacf2-104">Adaptación de actividades</span><span class="sxs-lookup"><span data-stu-id="bacf2-104">Activity Localization</span></span>  
 <span data-ttu-id="bacf2-105">Tal y como ocurre con todas las aplicaciones que deben adaptarse (distribuidas en versiones distintas para diferentes idiomas y referencias culturales), las cadenas que se vayan a mostrar al usuario no deberían ponerse directamente en código sino que deberían almacenarse en un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="bacf2-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="bacf2-106">Las cadenas, a continuación, pueden tener acceso mediante <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span><span class="sxs-lookup"><span data-stu-id="bacf2-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="bacf2-107">Si está desarrollando un componente que se distribuye en varios idiomas, querrá usar además cadenas de recursos para los mensajes de validación de actividad, datos de seguimiento definidos por el usuario, mensajes de traza y mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="bacf2-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="bacf2-108">En el siguiente ejercicio se muestra cómo usar un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="bacf2-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="bacf2-109">Usar archivos de recursos para cadenas adaptadas</span><span class="sxs-lookup"><span data-stu-id="bacf2-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="bacf2-110">En [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar...** , **Nuevo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="bacf2-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="bacf2-111">Seleccione **archivo de recursos** y un nombre al archivo ErrorResources.resx.</span><span class="sxs-lookup"><span data-stu-id="bacf2-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="bacf2-112">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bacf2-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="bacf2-113">Abra el archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="bacf2-113">Open the resource file.</span></span> <span data-ttu-id="bacf2-114">Agregar una nueva entrada con un **nombre** de ErrorString y un **valor** de "la actividad no es válida".</span><span class="sxs-lookup"><span data-stu-id="bacf2-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="bacf2-115">Agregue las instrucciones `using` siguientes a su clase.</span><span class="sxs-lookup"><span data-stu-id="bacf2-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="bacf2-116">Cree un administrador de recursos en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bacf2-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="bacf2-117">Reciba la cadena del administrador de recursos donde sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="bacf2-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="bacf2-118">El siguiente ejemplo de código muestra cómo usar las cadenas adaptadas en el método <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="bacf2-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
