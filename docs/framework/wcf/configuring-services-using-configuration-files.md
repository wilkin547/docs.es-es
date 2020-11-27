---
title: Configuración de servicios mediante archivos de configuración
description: Obtenga información sobre cómo un archivo de configuración para un servicio WCF ofrece la flexibilidad de proporcionar datos de punto de conexión y comportamiento de servicio durante la implementación.
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 25a6891564054878e7bdf7f43d431547ea1dee6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253354"
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="de785-103">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="de785-103">Configuring Services Using Configuration Files</span></span>

<span data-ttu-id="de785-104">La configuración de un servicio de Windows Communication Foundation (WCF) con un archivo de configuración ofrece la flexibilidad de proporcionar datos de punto de conexión y de comportamiento de servicio en el punto de implementación en lugar de en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="de785-104">Configuring a Windows Communication Foundation (WCF) service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="de785-105">En este tema se describen las principales técnicas disponibles.</span><span class="sxs-lookup"><span data-stu-id="de785-105">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="de785-106">Un servicio WCF se puede configurar mediante la tecnología de configuración de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de785-106">A WCF service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="de785-107">Normalmente, los elementos XML se agregan al archivo Web.config para un sitio Internet Information Services (IIS) que hospeda un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="de785-107">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="de785-108">Los elementos le permiten cambiar detalles como las direcciones de extremos (las direcciones reales utilizadas para comunicarse con el servicio) equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="de785-108">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="de785-109">Además, WCF incluye varios elementos proporcionados por el sistema que le permiten seleccionar rápidamente las características más básicas de un servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-109">In addition, WCF includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="de785-110">A partir de .NET Framework 4, WCF incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="de785-110">Starting with .NET Framework 4, WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="de785-111">Si no proporciona ninguna configuración de WCF para un servicio determinado, el tiempo de ejecución configura automáticamente el servicio con algunos extremos estándar y un enlace o comportamiento predeterminados.</span><span class="sxs-lookup"><span data-stu-id="de785-111">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="de785-112">En la práctica, escribir la configuración es una parte importante de la programación de aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="de785-112">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
 <span data-ttu-id="de785-113">Para obtener más información, consulte [configuración de enlaces para servicios](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="de785-113">For more information, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="de785-114">Para obtener una lista de los elementos que se usan con más frecuencia, vea [enlaces proporcionados por el sistema](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="de785-114">For a list of the most commonly used elements, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="de785-115">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="de785-115">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="de785-116">Al implementar escenarios en paralelo con dos versiones diferentes de un servicio, es necesario especificar los nombres parciales de los ensamblados a los que se hace referencia en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-116">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="de785-117">Esto se debe a que el archivo de configuración se comparte entre todas las versiones de un servicio y se podrían estar ejecutando con versiones diferentes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de785-117">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="de785-118">System.Configuration: Web.config y App.config</span><span class="sxs-lookup"><span data-stu-id="de785-118">System.Configuration: Web.config and App.config</span></span>  

 <span data-ttu-id="de785-119">WCF usa el sistema de configuración de System.Configprimario del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de785-119">WCF uses the System.Configuration configuration system of the .NET Framework.</span></span>  
  
 <span data-ttu-id="de785-120">Al configurar un servicio en Visual Studio, use un archivo de Web.config o un archivo de App.config para especificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-120">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="de785-121">El entorno de hospedaje determina la elección realizada del nombre del archivo de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-121">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="de785-122">Si está utilizando IIS para hospedar su servicio, utilice un archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="de785-122">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="de785-123">Si está utilizando cualquier otro entorno de hospedaje, utilice un archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="de785-123">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="de785-124">En Visual Studio, el archivo denominado App.config se usa para crear el archivo de configuración final.</span><span class="sxs-lookup"><span data-stu-id="de785-124">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="de785-125">El nombre final realmente utilizado para la configuración depende del nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de785-125">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="de785-126">Por ejemplo, un ensamblado denominado "Cohowinery.exe" tiene un nombre final de archivo de configuración de "Cohowinery.exe.config".</span><span class="sxs-lookup"><span data-stu-id="de785-126">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="de785-127">Sin embargo, solo necesita modificar el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="de785-127">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="de785-128">Los cambios realizados en ese archivo se realizan automáticamente en tiempo de compilación en el archivo final de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de785-128">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="de785-129">Al utilizar un archivo App.config, el sistema de configuración combina el archivo App.config con el contenido del archivo Machine.config cuando se inicia la aplicación y se aplica la configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-129">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="de785-130">Este mecanismo permite definir los valores de equipo en el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="de785-130">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="de785-131">El archivo App.config se puede utilizar para reemplazar los valores del archivo Machine.config; también puede bloquear los valores en el archivo Machine.config para que se utilicen.</span><span class="sxs-lookup"><span data-stu-id="de785-131">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="de785-132">En el caso de Web.config, el sistema de configuración combina los archivos Web.config de todos los directorios que conducen al directorio de la aplicación en la configuración que se aplica.</span><span class="sxs-lookup"><span data-stu-id="de785-132">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="de785-133">Para obtener más información sobre la configuración y las prioridades de configuración, vea los temas del <xref:System.Configuration> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="de785-133">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="de785-134">Secciones principales del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="de785-134">Major Sections of the Configuration File</span></span>  

 <span data-ttu-id="de785-135">Las secciones principales del archivo de configuración incluyen los elementos siguientes.</span><span class="sxs-lookup"><span data-stu-id="de785-135">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
> <span data-ttu-id="de785-136">Las secciones de enlaces y comportamientos son opcionales y solo se incluyen si son necesarias.</span><span class="sxs-lookup"><span data-stu-id="de785-136">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="de785-137">El \<services> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-137">The \<services> Element</span></span>  

 <span data-ttu-id="de785-138">El elemento `services` contiene las especificaciones para todos los servicios que la aplicación hospeda.</span><span class="sxs-lookup"><span data-stu-id="de785-138">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="de785-139">A partir del modelo de configuración simplificado en .NET Framework 4, esta sección es opcional.</span><span class="sxs-lookup"><span data-stu-id="de785-139">Starting with the simplified configuration model in .NET Framework 4, this section is optional.</span></span>  
  
 [\<services>](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="de785-140">El \<service> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-140">The \<service> Element</span></span>  

 <span data-ttu-id="de785-141">Cada elemento service tiene estos atributos:</span><span class="sxs-lookup"><span data-stu-id="de785-141">Each service has these attributes:</span></span>  
  
- <span data-ttu-id="de785-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="de785-142">`name`.</span></span> <span data-ttu-id="de785-143">Especifica el tipo que proporciona una implementación de un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="de785-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="de785-144">Este es un nombre completo que consta del espacio de nombres, un punto y el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="de785-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="de785-145">Por ejemplo, `"MyNameSpace.myServiceType"`.</span><span class="sxs-lookup"><span data-stu-id="de785-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
- <span data-ttu-id="de785-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="de785-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="de785-147">Especifica el nombre de uno de los elementos `behavior` encontrados en el elemento `behaviors` .</span><span class="sxs-lookup"><span data-stu-id="de785-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="de785-148">El comportamiento especificado rige las acciones como si el servicio permitiese la suplantación.</span><span class="sxs-lookup"><span data-stu-id="de785-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="de785-149">Si su valor es el nombre vacío o no se proporciona ningún atributo `behaviorConfiguration` , se agrega al servicio el conjunto predeterminado de comportamientos de servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
- [\<service>](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="de785-150">El \<endpoint> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-150">The \<endpoint> Element</span></span>  

 <span data-ttu-id="de785-151">Cada extremo requiere una dirección, un enlace y un contrato, que están representados por los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="de785-151">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
- <span data-ttu-id="de785-152">`address`.</span><span class="sxs-lookup"><span data-stu-id="de785-152">`address`.</span></span> <span data-ttu-id="de785-153">Especifica el Identificador uniforme de recursos (URI) del servicio, que puede ser una dirección absoluta o una relativa a la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-153">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="de785-154">Si está establecido en una cadena vacía, indica que el extremo está disponible en la dirección base que se especifica al crear <xref:System.ServiceModel.ServiceHost> para el servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-154">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
- <span data-ttu-id="de785-155">`binding`.</span><span class="sxs-lookup"><span data-stu-id="de785-155">`binding`.</span></span> <span data-ttu-id="de785-156">Normalmente especifica un enlace proporcionado por el sistema como <xref:System.ServiceModel.WSHttpBinding>, pero también puede especificar un enlace definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="de785-156">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="de785-157">El enlace especificado determina el tipo de transporte, seguridad y codificación utilizados y si se admiten o habilitan sesiones confiables, transacciones, o la transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="de785-157">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
- <span data-ttu-id="de785-158">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="de785-158">`bindingConfiguration`.</span></span> <span data-ttu-id="de785-159">Si se deben modificar los valores predeterminados de un enlace, esto se puede hacer configurando el elemento de `binding` adecuado en el elemento `bindings` .</span><span class="sxs-lookup"><span data-stu-id="de785-159">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="de785-160">Este atributo debería recibir el mismo valor que el atributo `name` del elemento de `binding` que se utiliza para cambiar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="de785-160">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="de785-161">Si no se proporciona ningún nombre, o no se especifica ningún atributo `bindingConfiguration` en el enlace, se usa el enlace predeterminado del tipo de enlace en el extremo.</span><span class="sxs-lookup"><span data-stu-id="de785-161">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
- <span data-ttu-id="de785-162">`contract`.</span><span class="sxs-lookup"><span data-stu-id="de785-162">`contract`.</span></span> <span data-ttu-id="de785-163">Especifica la interfaz que define el contrato.</span><span class="sxs-lookup"><span data-stu-id="de785-163">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="de785-164">Ésta es la interfaz implementada en el tipo de Common Language Runtime (CLR) especificado por el atributo `name` del elemento `service` .</span><span class="sxs-lookup"><span data-stu-id="de785-164">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
- [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="de785-165">El \<bindings> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-165">The \<bindings> Element</span></span>  

 <span data-ttu-id="de785-166">El elemento `bindings` contiene las especificaciones para todos los enlaces que puede utilizar cualquier extremo definido en cualquier servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-166">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [\<bindings>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="de785-167">El \<binding> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-167">The \<binding> Element</span></span>  

 <span data-ttu-id="de785-168">El elemento `binding` contenidos en el elemento `bindings` pueden ser uno de los enlaces proporcionados por el sistema (consulte [System-Provided Bindings](system-provided-bindings.md)) o un enlace personalizado (consulte [Custom Bindings](./extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="de785-168">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](system-provided-bindings.md)) or a custom binding (see [Custom Bindings](./extending/custom-bindings.md)).</span></span> <span data-ttu-id="de785-169">El elemento `binding` tiene un atributo `name` que pone en correlación el enlace con el extremo especificado en el atributo `bindingConfiguration` del elemento `endpoint` .</span><span class="sxs-lookup"><span data-stu-id="de785-169">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="de785-170">Si no se especifica ningún nombre, dicho enlace corresponde al enlace predeterminado de ese tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="de785-170">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
<span data-ttu-id="de785-171">Para obtener más información sobre la configuración de servicios y clientes, vea [configuración de servicios WCF](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="de785-171">For more information about configuring services and clients, see [Configuring WCF services](configuring-services.md).</span></span>
  
 [\<binding>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="de785-172">El \<behaviors> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-172">The \<behaviors> Element</span></span>  

 <span data-ttu-id="de785-173">Éste es un elemento contenedor para los elementos `behavior` que definen los comportamientos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-173">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="de785-174">El \<behavior> elemento</span><span class="sxs-lookup"><span data-stu-id="de785-174">The \<behavior> Element</span></span>  

 <span data-ttu-id="de785-175">Cada `behavior` elemento se identifica mediante un `name` atributo y proporciona un comportamiento proporcionado por el sistema, como <`throttling`> o un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="de785-175">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="de785-176">Si no se especifica ningún nombre, dicho elemento de comportamiento corresponde al servicio predeterminado o al comportamiento de extremo.</span><span class="sxs-lookup"><span data-stu-id="de785-176">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="de785-177">Uso de las configuraciones de comportamientos y enlaces</span><span class="sxs-lookup"><span data-stu-id="de785-177">How to Use Binding and Behavior Configurations</span></span>  

 <span data-ttu-id="de785-178">WCF facilita el uso compartido de las configuraciones entre los puntos de conexión mediante un sistema de referencia en la configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-178">WCF makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="de785-179">En lugar de asignar directamente los valores de configuración a un extremo, los valores de configuración relacionados con el enlace se agrupan en elementos `bindingConfiguration` de la sección `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="de785-179">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="de785-180">Una configuración de enlace es un grupo con nombre de valores en un enlace.</span><span class="sxs-lookup"><span data-stu-id="de785-180">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="de785-181">Entonces, los extremos pueden hacer referencia a `bindingConfiguration` por nombre.</span><span class="sxs-lookup"><span data-stu-id="de785-181">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint
          address="myAddress" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint
          address="myAddress2" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint
          address="myAddress3" binding="basicHttpBinding"
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="de785-182">El `name` de la `bindingConfiguration` se establece en el elemento `<binding>` .</span><span class="sxs-lookup"><span data-stu-id="de785-182">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="de785-183">El `name` debe ser una cadena única dentro del ámbito del tipo de enlace, en este caso el [<basicHttpBinding \> ](../configure-apps/file-schema/wcf/basichttpbinding.md), o un valor vacío para hacer referencia al enlace predeterminado.</span><span class="sxs-lookup"><span data-stu-id="de785-183">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="de785-184">El extremo vincula a la configuración estableciendo el atributo `bindingConfiguration` en esta cadena.</span><span class="sxs-lookup"><span data-stu-id="de785-184">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="de785-185">Una `behaviorConfiguration` se implementa de la misma manera, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="de785-185">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="de785-186">Observe que el conjunto predeterminado de comportamientos de servicio se agrega al servicio.</span><span class="sxs-lookup"><span data-stu-id="de785-186">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="de785-187">Este sistema permite a los extremos compartir configuraciones comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-187">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="de785-188">Si se requiere el ámbito de todo el equipo, cree la configuración de enlace o comportamiento en Machine.config. Los valores de configuración están disponibles en todos los archivos App.config.</span><span class="sxs-lookup"><span data-stu-id="de785-188">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="de785-189">[Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) facilita la creación de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="de785-189">The [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="de785-190">Combinación de comportamientos</span><span class="sxs-lookup"><span data-stu-id="de785-190">Behavior Merge</span></span>  

 <span data-ttu-id="de785-191">La característica de combinación de comportamientos simplifica la administración de los comportamientos cuando se desea el uso coherente de un conjunto de comportamientos comunes.</span><span class="sxs-lookup"><span data-stu-id="de785-191">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="de785-192">Esta característica permite especificar comportamientos en niveles diferentes de la jerarquía de configuración y hacer que los servicios hereden los comportamientos de varios niveles de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-192">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="de785-193">Para mostrar cómo funciona, supongamos que tiene el siguiente diseño de directorio virtual en IIS:</span><span class="sxs-lookup"><span data-stu-id="de785-193">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 <span data-ttu-id="de785-194">Y el `~\Web.config` archivo tiene el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="de785-194">And your `~\Web.config` file has the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="de785-195">Y tiene un archivo Web.config secundario ubicado en ~\Child\Web.config con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="de785-195">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="de785-196">El servicio ubicado en ~\Child\Service.svc se comportará como si tuviese los comportamientos de serviceMetadata y serviceDebug.</span><span class="sxs-lookup"><span data-stu-id="de785-196">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="de785-197">El servicio ubicado en ~\Service.svc tendrá solo el comportamiento de serviceDebug.</span><span class="sxs-lookup"><span data-stu-id="de785-197">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="de785-198">Lo que sucede es que se combinan las dos colecciones de comportamientos con el mismo nombre (en este caso, la cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="de785-198">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="de785-199">También puede borrar colecciones de comportamientos con la \<clear> etiqueta y quitar los comportamientos individuales de la colección mediante la \<remove> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="de785-199">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="de785-200">Por ejemplo, las dos configuraciones siguientes hacen que el servicio secundario tenga únicamente el comportamiento de serviceMetadata:</span><span class="sxs-lookup"><span data-stu-id="de785-200">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="de785-201">La combinación de comportamientos se lleva a cabo para colecciones de comportamientos sin nombre, como se muestra arriba, y colecciones de comportamientos con nombre.</span><span class="sxs-lookup"><span data-stu-id="de785-201">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="de785-202">La combinación de comportamientos funciona en el entorno de hospedaje de IIS, en el que Web.config los archivos se combinan jerárquicamente con el archivo raíz Web.config y machine.config. Pero también funciona en el entorno de la aplicación, donde machine.config puede fusionar mediante combinación con el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="de785-202">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="de785-203">La combinación de comportamientos se aplica a comportamientos de extremo y comportamientos de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="de785-203">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="de785-204">Si una colección de comportamientos secundarios contiene un comportamiento que ya se encuentra en la colección de comportamientos primarios, el comportamiento secundario invalida el primario.</span><span class="sxs-lookup"><span data-stu-id="de785-204">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="de785-205">Por tanto, si una colección de comportamientos primarios tuviera `<serviceMetadata httpGetEnabled="False" />` y una colección de comportamientos secundarios tuviese `<serviceMetadata httpGetEnabled="True" />` , el comportamiento secundario invalidaría el comportamiento primario en la colección de comportamientos y httpGetEnabled sería "true".</span><span class="sxs-lookup"><span data-stu-id="de785-205">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de785-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="de785-206">See also</span></span>

- [<span data-ttu-id="de785-207">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="de785-207">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="de785-208">Configuración de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="de785-208">Configuring WCF services</span></span>](configuring-services.md)
- [\<service>](../configure-apps/file-schema/wcf/service.md)
- [\<binding>](../configure-apps/file-schema/wcf/bindings.md)
