---
title: Programar el árbol de elementos de modelo
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: 059bb3edcfe41f52e2244ff6f5bf3fc78a4262bb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235810"
---
# <a name="programming-model-item-tree"></a>Programar el árbol de elementos de modelo

En este ejemplo se muestra cómo navegar por el <xref:System.Activities.Presentation.Model.ModelItem> árbol utilizando el enlace de datos declarativo de la vista de árbol Windows Presentation Foundation (WPF).

## <a name="sample-details"></a>Detalles del ejemplo

 El <xref:System.Activities.Presentation.Model.ModelItem> árbol es la abstracción que usa la infraestructura de diseñador de flujo de trabajo de Windows para exponer los datos sobre la instancia subyacente que se está editando. La ilustración siguiente es una representación de los distintos niveles de infraestructura dentro del Diseñador de flujo de trabajo.

 ![Diagrama que muestra la arquitectura de Diseñador de flujo de trabajo.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Un objeto <xref:System.Activities.Presentation.Model.ModelItem> consta de un puntero al valor subyacente, así como de una colección de objetos <xref:System.Activities.Presentation.Model.ModelProperty>. Un objeto <xref:System.Activities.Presentation.Model.ModelProperty> a su vez consta de datos como el nombre y tipo de la propiedad, y un puntero al valor que, a su vez, es otro objeto <xref:System.Activities.Presentation.Model.ModelItem>. Se utiliza un convertidor de valores para manipular algunos de los objetos <xref:System.Activities.Presentation.Model.ModelItem> que devuelve <xref:System.Activities.Presentation.Model.ModelProperty> para que aparezcan correctamente en la vista de árbol. A continuación, el ejemplo muestra cómo programar de manera imperativa en el árbol <xref:System.Activities.Presentation.Model.ModelItem> utilizando la sintaxis imperativa, tal y como se puede ver en el siguiente ejemplo.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Abra la solución ProgrammingModelItemTree. sln en Visual Studio 2010.

2. Para compilar la solución, seleccione **compilar solución** en el menú **compilar** .

3. Presione F5 para ejecutar la aplicación. A continuación, se muestra el formulario de WPF.

4. Haga clic en el botón **cargar WF** para cargar <xref:System.Activities.Presentation.Model.ModelItem> y enlazarlo a la vista de árbol.

5. Al hacer clic en el botón **cambiar árbol de elementos de modelo** , se ejecuta el código anterior para agregar un elemento al árbol y establecer una propiedad.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.IValueConverter>
