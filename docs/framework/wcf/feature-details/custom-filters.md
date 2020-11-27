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
# <a name="custom-filters"></a>Filtros personalizados

Los filtros personalizados le permiten definir una lógica coincidente que no se puede lograr mediante los filtros de mensajes proporcionados por el sistema. Por ejemplo, puede crear un filtro personalizado que aplique un algoritmo hash a un elemento de mensaje determinado y, a continuación, examine el valor para determinar si el filtro debería indicar verdadero o falso.  
  
## <a name="implementation"></a>Implementación  

 Un filtro personalizado es una implementación de la clase base abstracta <xref:System.ServiceModel.Dispatcher.MessageFilter>. Al implementar el filtro personalizado, el constructor puede aceptar un parámetro de cadena único de forma opcional. Este parámetro contiene la información de configuración que se pasa al constructor MessageFilter para proporcionar los valores o la configuración que necesite el filtro en el tiempo de ejecución para realizar las coincidencias. Por ejemplo, esto se puede usar para proporcionar un valor que el filtro deba buscar en el mensaje que se esté evaluando. En el siguiente ejemplo, se muestra una implementación básica de un filtro de mensajes personalizado que acepta un parámetro de cadena:  
  
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
> En una implementación real, los métodos de coincidencia contienen lógica que examinará el mensaje para determinar si este filtro de mensajes debe devolver **true** o **false**.  
  
### <a name="performance"></a>Rendimiento  

 Al implementar un filtro personalizado, es importante tener en cuenta el tiempo máximo requerido para que el filtro complete la evaluación de un mensaje. Puesto que un mensaje se puede evaluar con varios filtros antes de que se encuentre una coincidencia, es importante asegurarse de que la solicitud de cliente no expire antes de que se puedan evaluar todos los filtros. Por consiguiente un filtro personalizado debería contener solo el código necesario para evaluar el contenido o los atributos de un mensaje para determinar si coincide con los criterios de filtro.  
  
 En general, debería evitar lo siguiente al implementar un filtro personalizado:  
  
- La E/S, por ejemplo, guardar los datos en disco o en una base de datos.  
  
- El procesamiento innecesario, como recorrer varios registros en un documento.  
  
- Las operaciones de bloqueo, por ejemplo, las llamadas que implican obtener un bloqueo en recursos compartidos o realizar búsquedas con una base de datos.  
  
 Antes de utilizar un filtro personalizado en un entorno de producción, debería ejecutar pruebas de rendimiento para determinar el promedio de tiempo que el filtro tarda en evaluar un mensaje. Cuando se combina con el tiempo de proceso medio de los demás filtros que se usan en la tabla de filtro, esto le permitirá determinar con precisión el valor de tiempo de espera máximo que la aplicación cliente debería especificar.  
  
## <a name="usage"></a>Uso  

 Para usar el filtro personalizado con el servicio de enrutamiento, debe agregarlo a la tabla de filtros especificando una nueva entrada de filtro de tipo "Custom", el nombre de tipo completo del filtro de mensajes y el nombre del ensamblado.  Como con otros MessageFilters, puede especificar filterData de la cadena que se pasará al constructor del filtro personalizado.  
  
 En los siguientes ejemplos, se muestra cómo usar un filtro personalizado con el Servicio de enrutamiento:  
  
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
