---
title: Servicio de cuadro de herramientas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 816fb3a8964e5f990c496c73624ebb8c9c1053a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="toolbox-service"></a>Servicio de cuadro de herramientas
En este ejemplo se muestra cómo actualizar las actividades de Cuadro de herramientas de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] en función del contexto del flujo de trabajo. El ejemplo contiene un flujo de trabajo que cambia el contenido del Cuadro de herramientas si se selecciona una actividad personalizada.  
  
## <a name="discussion"></a>Explicación  
 Durante la creación de flujo de trabajo, por lo general los clientes desean que su cuadro de herramientas sea contextual. Por ejemplo, puede que el usuario desee asegurarse de que el Cuadro de herramientas muestra algunas actividades adicionales cuando se agrega una actividad específica al flujo de trabajo. Si las actividades se quitan del flujo de trabajo, el Cuadro de herramientas debe reaccionar adecuadamente en función de los requisitos de dominio.  
  
 En un diseñador de flujo de trabajo hospedado en otro host, el usuario controla el control Toolbox y puede asegurarse de que, en función de los cambios de modelo del flujo de trabajo, el host activa los cambios adecuados en el control Toolbox. Sin embargo, en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], el usuario no controla el Cuadro de herramientas, por lo que se necesita una interfaz para modificar su contenido. `IActivityToolboxService` es esa interfaz.  
  
 La API ofrece los cuatro métodos siguientes.  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución WorkflowSimulator.sln.  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Abra el archivo Workflow.xaml.  
  
4.  Agregar un **CustomActivity** arrastrando y colocando en el cuadro de herramientas. Tenga en cuenta que una categoría de cuadro de herramientas adicional denominada: **New WF Category** con una actividad **asignar**.  
  
5.  Ahora anule la selección de la **CustomActivity** arrastrando otra actividad en ella.  
  
6.  El elemento **asignar** en la categoría **New WF Category** en el cuadro de herramientas ahora se ha eliminado. Además, como ya no hay más elementos en la categoría, esta también se quita.  
  
7.  Seleccione el **CustomActivity** nuevo y la categoría y **asignar** actividad se vuelven a agregar.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
