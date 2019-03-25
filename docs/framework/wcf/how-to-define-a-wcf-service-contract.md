---
title: 'Tutorial: Definir un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: f93ef787c74a4581d45c24c5a704cc5fb044bd46
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409970"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Tutorial: Definir un contrato de servicio de Windows Communication Foundation

Este tutorial describen las primeras cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

Cuando se crea un servicio WCF, la primera tarea es definir un contrato de servicio. El contrato de servicio especifica qué operaciones admite el servicio. Una operación se puede considerar un método de servicio Web. Crear contratos de servicio mediante la definición de un objeto Visual C# o la interfaz de Visual Basic (VB). Una interfaz tiene las siguientes características:

- Cada método de la interfaz se corresponde con una operación de servicio concreta. 
- Para cada interfaz, se debe aplicar el <xref:System.ServiceModel.ServiceContractAttribute> atributo.
- Para cada operación o método, se debe aplicar el <xref:System.ServiceModel.OperationContractAttribute> atributo. 

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Crear un **biblioteca de servicios WCF** proyecto.
> - Defina una interfaz de contrato de servicio.


## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Crear un proyecto de biblioteca de servicios WCF y definir una interfaz de contrato de servicio

1. Abra Visual Studio como administrador. Para ello, seleccione el programa de Visual Studio en el **iniciar** menú y, a continuación, seleccione **más** > **ejecutar como administrador** en el menú contextual.

2. Crear un **biblioteca de servicios WCF** proyecto.

   1. En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

   2. En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione el **WCF** categoría. Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana. Seleccione **biblioteca de servicios WCF**.

      > [!NOTE]
      > Si no ve el **WCF** categoría de plantilla de proyecto, es posible que deba instalar el **Windows Communication Foundation** componente de Visual Studio. En el **nuevo proyecto** cuadro de diálogo, seleccione el **abrir Visual Studio Installer** vínculo en el lado izquierdo. Seleccione el **componentes individuales** ficha y, a continuación, busque y seleccione **Windows Communication Foundation** bajo el **las actividades de desarrollo** categoría. Elija **modificar** para empezar a instalar el componente.

   3. En la sección inferior de la ventana, escriba *GettingStartedLib* para el **nombre** y *GettingStarted* para el **nombre de la solución**. 

   4. Seleccione **Aceptar**.

      Visual Studio crea el proyecto, que tiene tres archivos: *IService1.cs* (o *IService1.vb* para un proyecto de Visual Basic), *Service1.cs* (o *Service1.vb* para un proyecto de Visual Basic), y  *App.config*. Visual Studio define estos archivos como sigue: 
      - El *IService1* archivo contiene la definición predeterminada del contrato de servicio. 
      - El *Service1* archivo contiene la implementación predeterminada del contrato de servicio. 
      - El *App.config* archivo contiene la información de configuración necesaria para cargar el servicio de forma predeterminada con la herramienta de Host de servicio WCF de Visual Studio. Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Si ha instalado Visual Studio con la configuración del entorno de desarrollo de Visual Basic, la solución podría estar oculto. Si esto es así, seleccione **opciones** desde el **herramientas** menú, a continuación, seleccione **proyectos y soluciones** > **General** en el **opciones** ventana. Seleccione **Mostrar solución siempre**. Además, compruebe que **guardar nuevos proyectos al crearlos** está seleccionada.


3. Desde **el Explorador de soluciones**, abra el **IService1.cs** o **IService1.vb** y reemplace su código con el código siguiente:

    ```csharp
    using System;
    using System.ServiceModel;

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

    ```vb
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

     Este contrato define una calculadora en línea. Tenga en cuenta la `ICalculator` interfaz se marca con el <xref:System.ServiceModel.ServiceContractAttribute> atributo (simplificada como `ServiceContract`). Este atributo define un espacio de nombres para eliminar la ambigüedad entre el nombre de contrato. El código marca cada operación de calculadora con los <xref:System.ServiceModel.OperationContractAttribute> atributo (simplificada como `OperationContract`).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> - Cree un proyecto de biblioteca de servicios WCF.
> - Defina una interfaz de contrato de servicio.

Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: Implementar un contrato de servicio WCF](how-to-implement-a-wcf-contract.md)
