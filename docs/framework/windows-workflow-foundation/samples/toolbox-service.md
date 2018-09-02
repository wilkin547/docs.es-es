---
title: Servicio de cuadro de herramientas
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b21f10c763f3f82591f947eb4cc48cf90f4ac79
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406467"
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
  
4.  Agregar un **CustomActivity** arrastrando y colocándola en el cuadro de herramientas. Tenga en cuenta que llama una categoría de cuadro de herramientas adicional: **New WF Category** con una actividad **asignar**.  
  
5.  Ahora anule la selección de la **CustomActivity** arrastrando otra actividad en ella.  
  
6.  El elemento **asignar** en la categoría **New WF Category** ahora se quita del cuadro de herramientas. Además, como ya no hay más elementos en la categoría, esta también se quita.  
  
7.  Seleccione el **CustomActivity** nuevo y la categoría y **asignar** actividad se vuelven a agregar.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
