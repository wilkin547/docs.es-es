---
description: 'Más información acerca de: ConfigurationCodeGenerator'
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: f65a32b6e9eadfed8dc8d1066086908c4b9a3396
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778365"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="5ae54-103">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="5ae54-103">ConfigurationCodeGenerator</span></span>

<span data-ttu-id="5ae54-104">ConfigurationCodeGenerator es una herramienta que puede utilizar para exponer sus implementaciones de canales personalizadas en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="5ae54-104">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="5ae54-105">Esto permite a los usuarios de su canal personalizado configurar el canal utilizando un archivo .config tal y como lo haría si configuraran un enlace proporcionado por el sistema como `NetTcpBinding` o un enlace personalizado usando `TcpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="5ae54-105">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="5ae54-106">Al escribir un canal personalizado y exponerlo en el modelo de programación usando un nuevo `BindingElement` o `Binding`, debe crear un conjunto de clases para convertir en configurable `BindingElement` o `Binding` utilizando un archivo .config.</span><span class="sxs-lookup"><span data-stu-id="5ae54-106">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="5ae54-107">Puede utilizar la herramienta ConfigurationCodeGenerator para generar estas clases y mejorar la experiencia de su cliente.</span><span class="sxs-lookup"><span data-stu-id="5ae54-107">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="5ae54-108">Para compilar la herramienta</span><span class="sxs-lookup"><span data-stu-id="5ae54-108">To build the tool</span></span>  
  
1. <span data-ttu-id="5ae54-109">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ae54-109">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="5ae54-110">Al compilar la solución se genera un archivo: ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="5ae54-110">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="5ae54-111">El archivo SampleRun. cmd tiene una línea de comandos de ejemplo que muestra cómo utilizar esta herramienta para generar las clases para el ejemplo [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="5ae54-111">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="5ae54-112">Para ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="5ae54-112">To run the tool</span></span>  
  
1. <span data-ttu-id="5ae54-113">En el símbolo del sistema escriba lo siguiente si tiene un tipo `BindingElement` personalizado y un tipo `Binding` personalizado:</span><span class="sxs-lookup"><span data-stu-id="5ae54-113">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="5ae54-114">O escriba lo siguiente si tiene sólo un tipo `BindingElement` personalizado:</span><span class="sxs-lookup"><span data-stu-id="5ae54-114">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="5ae54-115">O escriba lo siguiente si tiene sólo un tipo `Binding` personalizado:</span><span class="sxs-lookup"><span data-stu-id="5ae54-115">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="5ae54-116">El comando genera tres archivos .cs para `BindingElement` (si especificó la opción /be), cinco archivos .cs para el `Binding` estándar (si especificó la opción /sb:) y un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="5ae54-116">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1. <span data-ttu-id="5ae54-117">Si utilizó la opción /be, uno de los archivos .cs implementa `BindingElementExtensionSection` para su elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="5ae54-117">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="5ae54-118">Este código expone `BindingElement` en el sistema de configuración, para que otros enlaces personalizados puedan utilizar su elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="5ae54-118">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="5ae54-119">Los otros archivos tienen clases que representan valores predeterminados y constantes.</span><span class="sxs-lookup"><span data-stu-id="5ae54-119">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="5ae54-120">Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5ae54-120">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2. <span data-ttu-id="5ae54-121">Si especificó la opción /sb, dos de los archivos .cs implementan respectivamente `StandardBindingElement` y `StandardBindingCollectionElement`, que exponen el enlace estándar en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="5ae54-121">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="5ae54-122">Los otros archivos tienen clases que representan valores predeterminados y constantes.</span><span class="sxs-lookup"><span data-stu-id="5ae54-122">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="5ae54-123">Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5ae54-123">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="5ae54-124">Si especificó la opción/SB: CodeToAddTo \<*YourStdBinding*> . CS tiene código que debe agregar manualmente a la clase que implementa su enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="5ae54-124">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="5ae54-125">El archivo SampleConfig.xml contiene el código de configuración que debe agregar al archivo de configuración que registra los controladores definidos en el paso 1 o 2 anterior.</span><span class="sxs-lookup"><span data-stu-id="5ae54-125">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
