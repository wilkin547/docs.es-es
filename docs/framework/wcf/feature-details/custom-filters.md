---
title: Filtros personalizados
ms.date: 03/30/2017
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
ms.openlocfilehash: b5ec07c2e2a77c7de8b240d21b1eb54bf858b43b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258431"
---
# <a name="custom-filters"></a><span data-ttu-id="81a03-102">Filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="81a03-102">Custom Filters</span></span>

<span data-ttu-id="81a03-103">Los filtros personalizados le permiten definir una lógica coincidente que no se puede lograr mediante los filtros de mensajes proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="81a03-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="81a03-104">Por ejemplo, puede crear un filtro personalizado que aplique un algoritmo hash a un elemento de mensaje determinado y, a continuación, examine el valor para determinar si el filtro debería indicar verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="81a03-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="81a03-105">Implementación</span><span class="sxs-lookup"><span data-stu-id="81a03-105">Implementation</span></span>  

 <span data-ttu-id="81a03-106">Un filtro personalizado es una implementación de la clase base abstracta <xref:System.ServiceModel.Dispatcher.MessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="81a03-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="81a03-107">Al implementar el filtro personalizado, el constructor puede aceptar un parámetro de cadena único de forma opcional.</span><span class="sxs-lookup"><span data-stu-id="81a03-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="81a03-108">Este parámetro contiene la información de configuración que se pasa al constructor MessageFilter para proporcionar los valores o la configuración que necesite el filtro en el tiempo de ejecución para realizar las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="81a03-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="81a03-109">Por ejemplo, esto se puede usar para proporcionar un valor que el filtro deba buscar en el mensaje que se esté evaluando.</span><span class="sxs-lookup"><span data-stu-id="81a03-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="81a03-110">En el siguiente ejemplo, se muestra una implementación básica de un filtro de mensajes personalizado que acepta un parámetro de cadena:</span><span class="sxs-lookup"><span data-stu-id="81a03-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="81a03-111">En una implementación real, los métodos de coincidencia contienen lógica que examinará el mensaje para determinar si este filtro de mensajes debe devolver **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="81a03-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="81a03-112">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="81a03-112">Performance</span></span>  

 <span data-ttu-id="81a03-113">Al implementar un filtro personalizado, es importante tener en cuenta el tiempo máximo requerido para que el filtro complete la evaluación de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="81a03-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="81a03-114">Puesto que un mensaje se puede evaluar con varios filtros antes de que se encuentre una coincidencia, es importante asegurarse de que la solicitud de cliente no expire antes de que se puedan evaluar todos los filtros.</span><span class="sxs-lookup"><span data-stu-id="81a03-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="81a03-115">Por consiguiente un filtro personalizado debería contener solo el código necesario para evaluar el contenido o los atributos de un mensaje para determinar si coincide con los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="81a03-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="81a03-116">En general, debería evitar lo siguiente al implementar un filtro personalizado:</span><span class="sxs-lookup"><span data-stu-id="81a03-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
- <span data-ttu-id="81a03-117">La E/S, por ejemplo, guardar los datos en disco o en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="81a03-117">IO, such as saving data to disk or to a database.</span></span>  
  
- <span data-ttu-id="81a03-118">El procesamiento innecesario, como recorrer varios registros en un documento.</span><span class="sxs-lookup"><span data-stu-id="81a03-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
- <span data-ttu-id="81a03-119">Las operaciones de bloqueo, por ejemplo, las llamadas que implican obtener un bloqueo en recursos compartidos o realizar búsquedas con una base de datos.</span><span class="sxs-lookup"><span data-stu-id="81a03-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="81a03-120">Antes de utilizar un filtro personalizado en un entorno de producción, debería ejecutar pruebas de rendimiento para determinar el promedio de tiempo que el filtro tarda en evaluar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="81a03-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="81a03-121">Cuando se combina con el tiempo de proceso medio de los demás filtros que se usan en la tabla de filtro, esto le permitirá determinar con precisión el valor de tiempo de espera máximo que la aplicación cliente debería especificar.</span><span class="sxs-lookup"><span data-stu-id="81a03-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="81a03-122">Uso</span><span class="sxs-lookup"><span data-stu-id="81a03-122">Usage</span></span>  

 <span data-ttu-id="81a03-123">Para usar el filtro personalizado con el servicio de enrutamiento, debe agregarlo a la tabla de filtros especificando una nueva entrada de filtro de tipo "Custom", el nombre de tipo completo del filtro de mensajes y el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="81a03-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="81a03-124">Como con otros MessageFilters, puede especificar filterData de la cadena que se pasará al constructor del filtro personalizado.</span><span class="sxs-lookup"><span data-stu-id="81a03-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="81a03-125">En los siguientes ejemplos, se muestra cómo usar un filtro personalizado con el Servicio de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="81a03-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"
            customType="CustomAssembly.MyMessageFilter,
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```
