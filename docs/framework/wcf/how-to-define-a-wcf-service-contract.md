---
title: Definición de un contrato de servicio de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537883"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Definición de un contrato de servicio de Windows Communication Foundation

Se trata de la primera de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).

 Al crear un servicio WCF, la primera tarea es definir un contrato de servicio. El contrato de servicio especifica qué operaciones admite el servicio. Una operación se puede considerar un método de servicio Web. Los contratos se crean mediante la definición de una interfaz de C++, C# o Visual Basic (VB). Cada método de la interfaz se corresponde con una operación de servicio concreta. Cada interfaz debe tener <xref:System.ServiceModel.ServiceContractAttribute> aplicado y cada operación debe tener el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado. Si un método de una interfaz que tiene el atributo <xref:System.ServiceModel.ServiceContractAttribute> no tiene el atributo <xref:System.ServiceModel.OperationContractAttribute>, el servicio no expone ese método.

 El código utilizado para esta tarea se proporciona en el ejemplo que sigue al procedimiento.

## <a name="define-a-service-contract"></a>Definir un contrato de servicio

1. Abra Visual Studio como administrador haciendo clic con el programa en el **iniciar** menú y seleccionando **más** > **ejecutar como administrador**.

2. Cree un proyecto de biblioteca de servicios WCF.

   1. En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.

   2. En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione el **WCF** categoría. En la sección central del cuadro de diálogo se muestra una lista de plantillas de proyecto. Seleccione **biblioteca de servicios WCF**.

   3. Escriba `GettingStartedLib` en el **nombre** textbox y `GettingStarted` en el **nombre de la solución** cuadro de texto en la parte inferior del cuadro de diálogo.

   > [!NOTE]
   > Si no ve el **WCF** categoría de plantilla de proyecto, es posible que deba instalar el **Windows Communication Foundation** componente de Visual Studio. En el **nuevo proyecto** diálogo cuadro, haga clic en el vínculo que dice **instalador de Visual Studio abierto**. Seleccione el **componentes individuales** ficha y, a continuación, busque y seleccione **Windows Communication Foundation** bajo el **las actividades de desarrollo** categoría. Elija **modificar** para empezar a instalar el componente.

   Visual Studio crea el proyecto, que contiene 3 archivos: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) y App.config. El archivo IService1 contiene un contrato de servicio predeterminado. El archivo Service1 contiene una implementación predeterminada del contrato de servicio. El archivo App.config contiene la configuración necesaria para cargar el servicio predeterminado con el host de servicio WCF de Visual Studio. Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

3. Abra el archivo IService1.cs o IService1.vb y elimine el código dentro de la declaración de espacio de nombres, dejando la declaración de espacio de nombres. Dentro de la declaración de espacio de nombres se define una nueva interfaz denominada `ICalculator` como se muestra en el código siguiente.

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

     Este contrato define una calculadora en línea. Observe que la interfaz `ICalculator` se marca con el atributo <xref:System.ServiceModel.ServiceContractAttribute>. Este atributo define un espacio de nombres que se usa para eliminar la ambigüedad del nombre del contrato. Cada operación de calculadora se marca con el atributo <xref:System.ServiceModel.OperationContractAttribute>.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Cómo: implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Cómo implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)