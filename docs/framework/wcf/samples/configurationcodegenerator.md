---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: b8496992c7b0694a07ac047ba8537c67fc363c02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264236"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="c494a-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="c494a-102">ConfigurationCodeGenerator</span></span>

<span data-ttu-id="c494a-103">ConfigurationCodeGenerator es una herramienta que puede utilizar para exponer sus implementaciones de canales personalizadas en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="c494a-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="c494a-104">Esto permite a los usuarios de su canal personalizado configurar el canal utilizando un archivo .config tal y como lo haría si configuraran un enlace proporcionado por el sistema como `NetTcpBinding` o un enlace personalizado usando `TcpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="c494a-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="c494a-105">Al escribir un canal personalizado y exponerlo en el modelo de programación usando un nuevo `BindingElement` o `Binding`, debe crear un conjunto de clases para convertir en configurable `BindingElement` o `Binding` utilizando un archivo .config.</span><span class="sxs-lookup"><span data-stu-id="c494a-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="c494a-106">Puede utilizar la herramienta ConfigurationCodeGenerator para generar estas clases y mejorar la experiencia de su cliente.</span><span class="sxs-lookup"><span data-stu-id="c494a-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="c494a-107">Para compilar la herramienta</span><span class="sxs-lookup"><span data-stu-id="c494a-107">To build the tool</span></span>  
  
1. <span data-ttu-id="c494a-108">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c494a-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="c494a-109">Al compilar la solución se genera un archivo: ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="c494a-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="c494a-110">El archivo SampleRun. cmd tiene una línea de comandos de ejemplo que muestra cómo utilizar esta herramienta para generar las clases para el ejemplo [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="c494a-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="c494a-111">Para ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="c494a-111">To run the tool</span></span>  
  
1. <span data-ttu-id="c494a-112">En el símbolo del sistema escriba lo siguiente si tiene un tipo `BindingElement` personalizado y un tipo `Binding` personalizado:</span><span class="sxs-lookup"><span data-stu-id="c494a-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="c494a-113">O escriba lo siguiente si tiene sólo un tipo `BindingElement` personalizado:</span><span class="sxs-lookup"><span data-stu-id="c494a-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="c494a-114">O escriba lo siguiente si tiene sólo un tipo `Binding` personalizado:</span><span class="sxs-lookup"><span data-stu-id="c494a-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="c494a-115">El comando genera tres archivos .cs para `BindingElement` (si especificó la opción /be), cinco archivos .cs para el `Binding` estándar (si especificó la opción /sb:) y un archivo .xml.</span><span class="sxs-lookup"><span data-stu-id="c494a-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1. <span data-ttu-id="c494a-116">Si utilizó la opción /be, uno de los archivos .cs implementa `BindingElementExtensionSection` para su elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c494a-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="c494a-117">Este código expone `BindingElement` en el sistema de configuración, para que otros enlaces personalizados puedan utilizar su elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c494a-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="c494a-118">Los otros archivos tienen clases que representan valores predeterminados y constantes.</span><span class="sxs-lookup"><span data-stu-id="c494a-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="c494a-119">Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c494a-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2. <span data-ttu-id="c494a-120">Si especificó la opción /sb, dos de los archivos .cs implementan respectivamente `StandardBindingElement` y `StandardBindingCollectionElement`, que exponen el enlace estándar en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="c494a-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="c494a-121">Los otros archivos tienen clases que representan valores predeterminados y constantes.</span><span class="sxs-lookup"><span data-stu-id="c494a-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="c494a-122">Los archivos tienen los comentarios `//TODO` para recordarle actualizar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c494a-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="c494a-123">Si especificó la opción/SB: CodeToAddTo \<*YourStdBinding*> . CS tiene código que debe agregar manualmente a la clase que implementa su enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="c494a-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="c494a-124">El archivo SampleConfig.xml contiene el código de configuración que debe agregar al archivo de configuración que registra los controladores definidos en el paso 1 o 2 anterior.</span><span class="sxs-lookup"><span data-stu-id="c494a-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
