---
title: "Informaci&#243;n general sobre declaraciones de enlaces | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlazar datos, declaraciones"
  - "declaraciones de enlaces"
  - "enlace de datos, declaraciones"
  - "extensiones de marcado"
  - "sintaxis de elementos de objeto"
  - "sintaxis, elementos de objeto"
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Informaci&#243;n general sobre declaraciones de enlaces
En este tema se describen las distintas maneras de declarar un enlace.  
  
   
  
<a name="Prereq"></a>   
## Requisitos previos  
 Antes de leer este tema, es importante estar familiarizado con el concepto y el uso de las extensiones de marcado.  Para obtener más información sobre las extensiones de marcado, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 En este tema no se abordan los conceptos de enlace de datos.  Para obtener una explicación de los conceptos de enlace de datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="BindinginXAML"></a>   
## Declarar un enlace en XAML  
 En esta sección se explica cómo declarar un enlace en XAML.  
  
<a name="MarkupExtensionSyntax"></a>   
### Uso de extensiones de marcado  
 <xref:System.Windows.Data.Binding> es una extensión de marcado.  Cuando se utiliza la extensión de enlace para declarar un enlace, la declaración consiste en una serie de cláusulas que se sitúan tras la palabra clave `Binding` y están separadas por comas \(,\).  Las cláusulas de la declaración de enlace pueden estar en cualquier orden y hay muchas combinaciones posibles.  Las cláusulas son pares de valores *Nombre*\=*Valor*, donde *Nombre* es el nombre de la propiedad <xref:System.Windows.Data.Binding> y *Valor* es el valor que se establece para la propiedad.  
  
 Al crear cadenas de declaración de enlace en el marcado, deben asociarse a la [propiedad de dependencia](GTMT) concreta de un objeto de destino.  En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> mediante la extensión de enlace, especificando las propiedades <xref:System.Windows.Data.Binding.Source%2A> y <xref:System.Windows.Data.Binding.Path%2A>.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Puede especificar la mayoría de las propiedades de la clase <xref:System.Windows.Data.Binding> de este modo.  Para obtener más información sobre la extensión de enlace y una lista de propiedades de <xref:System.Windows.Data.Binding> que no se pueden establecer por medio de ella, vea la información general [Enlazar extensión de marcado](../../../../docs/framework/wpf/advanced/binding-markup-extension.md).  
  
<a name="ObjectElementSyntax"></a>   
### Sintaxis de elementos de objeto  
 La sintaxis de elementos de objeto es una alternativa a la creación de la declaración de enlace.  En la mayoría de los casos, utilizar la extensión de marcado o la sintaxis de elementos de objeto no aporta ninguna ventaja concreta.  Sin embargo, en aquellos casos en que la extensión de marcado no admite el escenario, como cuando el tipo del valor de propiedad no es de cadena y no existe ninguna conversión de tipos para él, es preciso utilizar la sintaxis de elementos de objeto.  
  
 A continuación, se muestra un ejemplo de sintaxis de elementos de objeto y de uso de la extensión de marcado:  
  
 [!code-xml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 En el ejemplo se enlaza la propiedad <xref:System.Windows.Controls.TextBlock.Foreground%2A> declarando un enlace mediante la sintaxis de extensiones.  La declaración de enlace de la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> utiliza la sintaxis de elementos de objeto.  
  
 Para obtener información acerca de los distintos términos utilizados, vea [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="MBandPB"></a>   
### MultiBinding y PriorityBinding  
 <xref:System.Windows.Data.MultiBinding> y <xref:System.Windows.Data.PriorityBinding> no admiten la sintaxis de extensión XAML.  Por consiguiente, debe utilizar la sintaxis de elementos de objeto para declarar <xref:System.Windows.Data.MultiBinding> o <xref:System.Windows.Data.PriorityBinding> en XAML.  
  
<a name="BindinginCode"></a>   
## Crear un enlace mediante código  
 Otra manera de especificar un enlace consiste en establecer directamente las propiedades de un objeto <xref:System.Windows.Data.Binding> mediante código.  En el ejemplo siguiente, se muestra cómo crear un objeto <xref:System.Windows.Data.Binding> y especificar las propiedades mediante código.  En este ejemplo, `TheConverter` es un objeto que implementa la interfaz <xref:System.Windows.Data.IValueConverter>.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
[!code-csharp[BindConversion#end1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#end1)]
[!code-vb[BindConversion#end1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#end1)]  
  
 Si el objeto que se enlaza es <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede llamar directamente al método `SetBinding` del objeto en lugar de utilizar <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName>.  Para obtener un ejemplo, vea [Crear un enlace mediante código](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).  
  
<a name="Path_Syntax"></a>   
## Sintaxis de ruta de acceso enlace  
 Utilice la propiedad <xref:System.Windows.Data.Binding.Path%2A> para especificar el valor del origen al que desea enlazar:  
  
-   En el caso más simple, el valor de propiedad <xref:System.Windows.Data.Binding.Path%2A> es el nombre de la propiedad del objeto de origen que se usará para el enlace, como `Path=PropertyName`.  
  
-   Las subpropiedades de una propiedad se pueden especificar mediante una sintaxis parecida, como en [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)].  Por ejemplo, la cláusula `Path=ShoppingCart.Order` establece el enlace a la subpropiedad `Order` del objeto o la propiedad `ShoppingCart`.  
  
-   Para enlazar a una [propiedad adjunta](GTMT), coloque la [propiedad adjunta](GTMT) entre paréntesis.  Por ejemplo, para enlazar a la [propiedad adjunta](GTMT) <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>, la sintaxis es `Path=(DockPanel.Dock)`.  
  
-   Los indizadores de una propiedad se pueden especificar entre corchetes después del nombre de la propiedad donde se aplica el indizador.  Por ejemplo, la cláusula `Path=ShoppingCart[0]` establece el enlace al índice que corresponde a cómo se administra la cadena literal "0" en la indización interna de la propiedad.  También se admiten indizadores anidados.  
  
-   Los indizadores y las subpropiedades se pueden mezclar en una cláusula `Path`; por ejemplo, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`  
  
-   Dentro de los indizadores puede tener varios parámetros de indizador separados por comas \(,\).  El tipo de cada parámetro se puede especificar con paréntesis.  Por ejemplo, puede tener `Path="[(sys:Int32)42,(sys:Int32)24]"`, donde `sys` se asigna al espacio de nombres `System`.  
  
-   Cuando el origen es una vista de colección, el elemento actual puede especificarse con una barra diagonal \(\/\).  Por ejemplo, la cláusula `Path=/` establece el enlace en el elemento actual de la vista.  Cuando el origen es una colección, esta sintaxis especifica el elemento actual de la vista de colección predeterminada.  
  
-   Se pueden combinar nombres de propiedad y barras diagonales para recorrer las propiedades que son colecciones.  Por ejemplo, `Path=/Offices/ManagerName` especifica el elemento actual de la colección de origen, que contiene una propiedad `Offices` que también es una colección.  Su elemento actual es un objeto que contiene una propiedad `ManagerName`.  
  
-   Opcionalmente, se puede usar una ruta de acceso con punto \(.\) para enlazar al origen actual.  Por ejemplo, `Text="{Binding}"` es equivalente a `Text="{Binding Path=.}"`.  
  
### Mecanismo de escape  
  
-   Dentro de los indizadores \(\[ \]\), el carácter de intercalación \(^\) es el carácter de escape para el carácter siguiente.  
  
-   Si establece <xref:System.Windows.Data.Binding.Path%2A> en XAML, también deberá marcar con caracteres de escape \(mediante entidades XML\) algunos caracteres especiales de la definición del lenguaje XML:  
  
    -   Utilice `&` como secuencia de escape para el carácter "&".  
  
    -   Utilice `>` como secuencia de escape de la etiqueta de cierre"\>".  
  
-   Además, si describe el enlace completo en un atributo utilizando la sintaxis de extensión de marcado, deberá utilizar un mecanismo de escape \(usando la barra diagonal inversa \\\) para los caracteres especiales del analizador de extensión de marcado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
    -   La barra diagonal inversa \(\\\) es el propio carácter de escape.  
  
    -   El signo igual \(\=\) separa el nombre de propiedad del valor de propiedad.  
  
    -   La coma \(,\) separa las propiedades.  
  
    -   La llave de cierre \(}\) es el fin de una extensión de marcado.  
  
<a name="Default"></a>   
## Comportamientos predeterminados  
 El comportamiento predeterminado el siguiente si no se especifica en la declaración.  
  
-   Se crea un convertidor predeterminado que intenta hacer una conversión de tipos entre el valor del [origen de enlace](GTMT) y el valor del [destino de enlace](GTMT).  Si no se puede realizar una conversión, el convertidor predeterminado devuelve `null`.  
  
-   Si no se establece <xref:System.Windows.Data.Binding.ConverterCulture%2A>, el motor de enlace utiliza la propiedad `Language` del objeto de [destino de enlace](GTMT).  En XAML, el valor predeterminado se establece en "en\-US" o se hereda del elemento raíz \(o de cualquier elemento\) de la página, si se ha establecido explícitamente.  
  
-   Siempre que el enlace tenga ya un contexto de datos \(por ejemplo, el contexto de datos heredado procedente de un elemento primario\), y que el elemento o la colección que ese contexto devuelva sea adecuado para el enlace sin requerir ninguna modificación ulterior de la ruta, una declaración de enlace puede no tener ninguna cláusula: `{Binding}`. Con frecuencia, los enlaces para estilos de datos se especifican de este modo, donde el enlace actúa en una colección.  Para obtener más información, vea la sección "Utilizar objetos completos como origen de enlace" en [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
-   El valor predeterminado de la propiedad <xref:System.Windows.Data.Binding.Mode%2A> puede ser unidireccional y bidireccional, según la [propiedad de dependencia](GTMT) que se enlace.  Siempre puede declarar explícitamente el modo de enlace, para asegurarse de que su comportamiento sea el deseado.  En general, las propiedades de control que puede modificar el usuario, como <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> y <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=fullName>, tienen como valor predeterminado enlaces bidireccionales, mientras que la mayoría de las demás propiedades tienen como valor predeterminado enlaces unidireccionales.  
  
-   El valor predeterminado de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> varía entre <xref:System.Windows.Data.UpdateSourceTrigger> y <xref:System.Windows.Data.UpdateSourceTrigger>, también según la [propiedad de dependencia](GTMT) enlazada.  El valor predeterminado de la mayoría de las [propiedades de dependencia](GTMT) es <xref:System.Windows.Data.UpdateSourceTrigger>, mientras que la propiedad <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> tiene un valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger>.  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Sintaxis de PropertyPath de XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)