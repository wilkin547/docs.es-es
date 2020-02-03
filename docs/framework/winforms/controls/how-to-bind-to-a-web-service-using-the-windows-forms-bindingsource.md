---
title: Enlazar a un servicio Web mediante BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: 0680c73e578577cf40158761f6c635fe30ff9f4d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746671"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a>Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios Windows Forms
Si quiere enlazar un control de Windows Forms a los resultados obtenidos de la llamada a un servicio Web XML, puede usar un componente <xref:System.Windows.Forms.BindingSource>. Este procedimiento es similar a enlazar un componente <xref:System.Windows.Forms.BindingSource> a un tipo. Debe crear un proxy de cliente que contenga los métodos y los tipos expuestos por el servicio Web. El proxy de cliente se genera desde el propio servicio Web (.asmx) o desde su archivo de lenguaje de descripción de servicios Web (WSDL). Además, el proxy de cliente debe exponer los campos de tipos complejos usados por el servicio Web como propiedades públicas. Después, enlace el <xref:System.Windows.Forms.BindingSource> a uno de los tipos expuestos en el proxy de servicio Web.  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a>Para crear y enlazar a un proxy de cliente  
  
1. Cree Windows Form en el directorio que elija, con un espacio de nombres adecuado.  
  
2. Agregue un componente <xref:System.Windows.Forms.BindingSource> al formulario.  
  
3. Abra el símbolo del sistema del kit de desarrollo de software (SDK) de Windows y vaya al mismo directorio en el que se encuentra el formulario.  
  
4. En la herramienta WSDL, escriba `wsdl` y la dirección URL del archivo .asmx o WSDL del servicio web, seguido por el espacio de nombres de la aplicación y, opcionalmente, el lenguaje con el que está trabajando.  
  
     En el ejemplo de código siguiente se usa el servicio Web ubicado en `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`. Por ejemplo, para C# escriba `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, o para Visual Basic escriba `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`. Al pasar la ruta de acceso como un argumento a la herramienta WSDL, se generará un proxy de cliente en el mismo directorio y espacio de nombres que la aplicación, en el lenguaje especificado. Si usa Visual Studio, agregue el archivo al proyecto.  
  
5. En el proxy de cliente, seleccione el tipo al que se enlazará.  
  
     Suele ser un tipo devuelto por un método proporcionado por el servicio Web. Los campos del tipo elegido se deben exponer como propiedades públicas con fines de enlace.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6. Establezca la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> del <xref:System.Windows.Forms.BindingSource> en el tipo que quiera que esté contenido en el proxy de cliente del servicio Web.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a>Para enlazar controles al BindingSource que está enlazado a un servicio Web  
  
- Enlace controles al <xref:System.Windows.Forms.BindingSource>, pasando como parámetro la propiedad pública del tipo de servicio Web que desee.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo enlazar un componente <xref:System.Windows.Forms.BindingSource> a un servicio Web y, después, cómo enlazar un cuadro de texto al componente <xref:System.Windows.Forms.BindingSource>. Al hacer clic en el botón, se llama a un método de servicio Web y el resultado se mostrarán en `textbox1`.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este es un ejemplo completo que incluye un método `Main` y una versión reducida del código del proxy de cliente.  
  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing, System.Web.Services, System.Windows.Forms y System.Xml.  
  
## <a name="see-also"></a>Consulte también

- [Componente BindingSource](bindingsource-component.md)
- [Cómo: Enlazar un control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
