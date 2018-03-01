---
title: "Definición de un contrato de servicio de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c69f79d8629acee80a2e59346032e7733ec37dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Definición de un contrato de servicio de Windows Communication Foundation
Es la primera de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.  
  
 Al crear un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la primera tarea es definir un contrato de servicio. El contrato de servicio especifica qué operaciones admite el servicio. Una operación se puede considerar un método de servicio Web. Los contratos se crean mediante la definición de una interfaz de C++, C# o Visual Basic (VB). Cada método de la interfaz se corresponde con una operación de servicio concreta. Cada interfaz debe tener <xref:System.ServiceModel.ServiceContractAttribute> aplicado y cada operación debe tener el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado. Si un método de una interfaz que tiene el atributo <xref:System.ServiceModel.ServiceContractAttribute> no tiene el atributo <xref:System.ServiceModel.OperationContractAttribute>, el servicio no expone ese método.  
  
 El código utilizado para esta tarea se proporciona en el ejemplo que sigue al procedimiento.  
  
### <a name="to-define-a-service-contract"></a>Para definir un contrato de servicio  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] como administrador haciendo clic en el programa en el **iniciar** menú y seleccionando **ejecutar como administrador**.  
  
2.  Crear un proyecto de biblioteca de servicios WCF, haga clic en el **archivo** menú y seleccionando **New**, **proyecto**. En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo del cuadro de diálogo expandir **Visual C#** para un proyecto de C# o **otros lenguajes** y, a continuación, **Visual Basic** para un proyecto de Visual Basic. En el idioma seleccionado, seleccione **WCF** y se mostrará una lista de plantillas de proyecto en la sección central del cuadro de diálogo. Seleccione **biblioteca de servicios WCF**y el tipo de `GettingStartedLib` en el **nombre** cuadro de texto y `GettingStarted` en el **nombre de la solución** cuadro de texto en la parte inferior del cuadro de diálogo.  
  
3.  Visual Studio creará el proyecto que contiene 3 archivos: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) y App.config.  El archivo IService1 contiene un contrato de servicio predeterminado.  El archivo Service1 contiene una implementación predeterminada del contrato de servicio. El archivo App.config contiene la configuración necesaria para cargar el servicio predeterminado con el host de servicio WCF de Visual Studio. Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
4.  Abra el archivo IService1.cs o IService1.vb y elimine el código dentro de la declaración de espacio de nombres que sale de la declaración de espacio de nombres. Dentro de la declaración de espacio de nombres se define una nueva interfaz denominada `ICalculator` como se muestra en el código siguiente.  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
            public interface ICalculator  
            {  
                [OperationContract]  
                double Add(double n1, double n2);  
                [OperationContract]  
                double Subtract(double n1, double n2);  
                [OperationContract]  
                double Multiply(double n1, double n2);  
                [OperationContract]  
                double Divide(double n1, double n2);  
            }  
    }  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
    ```  
  
     Este contrato define una calculadora en línea. Observe que la interfaz `ICalculator` se marca con el atributo <xref:System.ServiceModel.ServiceContractAttribute>. Este atributo define un espacio de nombres que se usa para eliminar la ambigüedad del nombre del contrato. Cada operación de calculadora se marca con el atributo <xref:System.ServiceModel.OperationContractAttribute>.  
  
    > [!NOTE]
    >  Al usar los atributos para anotar una interfaz, miembro o clase, puede quitar la parte "Attribute" del nombre de atributo. Por tanto, la clase <xref:System.ServiceModel.ServiceContractAttribute> se convierte en `[ServiceContract]` en C# o `<ServiceContract>` en Visual Basic.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
