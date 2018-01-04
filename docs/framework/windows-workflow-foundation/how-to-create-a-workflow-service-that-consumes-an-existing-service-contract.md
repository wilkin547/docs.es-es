---
title: Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a754875dc3f7968086f4f92044205b8ebceb01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero. La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First. La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.  
  
> [!NOTE]
>  Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero. [!INCLUDE[crabout](../../../includes/crabout-md.md)]desarrollo de servicios de flujo de trabajo de contrato primero, consulte [desarrollo de servicios de flujo de trabajo de primer contrato](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Crear el proyecto de flujo de trabajo  
  
1.  En [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], seleccione **archivo**, **nuevo proyecto**. Seleccione el **WCF** nodo bajo el **C#** nodo en el **plantillas** del árbol y seleccione la **aplicación de servicio de flujo de trabajo de WCF** plantilla.  
  
2.  Asigne al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.  
  
### <a name="creating-the-service-contract"></a>Crear el contrato de servicio  
  
1.  Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** . Seleccione el **código** nodo a la izquierda y la **clase** plantilla a la derecha. La nueva clase el nombre `IBookService` y haga clic en **Aceptar**.  
  
2.  En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  Compile el proyecto presionando **Ctrl + Mayús + B**.  
  
### <a name="importing-the-service-contract"></a>Importar el contrato de servicio  
  
1.  Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **contrato de servicio de importación**. En  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**. Haga clic en **Aceptar**.  
  
2.  Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto. Haga clic en **Aceptar**.  
  
3.  Compile el proyecto presionando **Ctrl + Mayús + B**, de modo que las actividades importadas aparecerán en el cuadro de herramientas.  
  
4.  En **el Explorador de soluciones**, abra Service1.xamlx. El servicio de flujo de trabajo aparecerá en el diseñador.  
  
5.  Seleccione el **secuencia** actividad. En la ventana Propiedades, haga clic en el **...** botón en el **ImplementedContract** propiedad. En el **Editor de la colección de tipo** ventana que aparece, haga clic en el **tipo** lista desplegable y seleccione el **buscar tipos...** entrada. En el **examinar y seleccionar .net tipo** cuadro de diálogo, en  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**. Haga clic en **Aceptar**. En el **Editor de la colección de tipo** cuadro de diálogo, haga clic en **Aceptar**.  
  
6.  Seleccione y elimine la **ReceiveRequest** y **SendResponse** actividades.  
  
7.  En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y un **Checkout_Receive** actividad en el **servicio secuencial** actividad.
