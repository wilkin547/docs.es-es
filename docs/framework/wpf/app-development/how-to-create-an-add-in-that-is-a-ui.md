---
title: "C&#243;mo: Crear un complemento que sea una interfaz de usuario | Microsoft Docs"
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
  - "crear un complemento que sea una interfaz de usuario [WPF]"
  - "complementos [WPF], interfaz de usuario"
  - "crear complementos de interfaz de usuario [WPF]"
  - "Interfaz de usuario complementos [WPF], crear"
  - "implementar complementos de interfaz de usuario [WPF]"
  - "segmentos de canalización [WPF], crear complementos"
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear un complemento que sea una interfaz de usuario
\<?xml version="1.0" encoding="utf-8"?>
\<developerHowToDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Este ejemplo muestra cómo crear un complemento es un <token>TLA #tla_wpf</token> <token>TLA #tla_ui</token> que está hospedado por un <token>TLA&#2;tla_wpf</token> aplicación independiente.</para> 
    <para>El complemento es un <token>TLA&#2;tla_ui</token> que es un <token>TLA&#2;tla_wpf</token> control de usuario. El contenido del control de usuario es un botón único que, al hacer clic, muestra un cuadro de mensaje. El <token>TLA&#2;tla_wpf</token> aplicación independiente que hospeda el complemento <token>TLA&#2;tla_ui</token> como el contenido de la ventana principal de la aplicación.</para> 
    <para> 
      <embeddedLabel>Requisitos previos</embeddedLabel>
    </para>
    <para>Este ejemplo destaca la <token>TLA&#2;tla_wpf</token> extensiones a la <token>dnprdnshort</token> modelo de complemento que habilitan este escenario y se supone lo siguiente:</para>
    <list class="bullet">
      <listItem>
        <para>conocimiento de la <token>dnprdnshort</token> modelo de complemento, incluida la canalización, complemento y desarrollo de host. Si no está familiarizado con estos conceptos, consulte \<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">complementos y extensibilidad</legacyLink>. Para obtener un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte \<legacyLink xlink:href="694a33c5-a040-450d-aed5-ac49fc88ce61">Tutorial: crear una aplicación Extensible</legacyLink>.</para> 
      </listItem> 
      <listItem> 
        <para>Conocimiento de la <token>TLA&#2;tla_wpf</token> extensiones a la <token>dnprdnshort</token> modelo de complemento, que puede encontrar aquí: \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">WPF Add-Ins Overview</link>.</para> 
      </listItem> 
    </list> 
  </introduction> 
  <codeExample> 
    <legacy> 
      <content> 
        <para>Para crear un complemento es un <token>TLA&#2;tla_wpf</token> <token>TLA&#2;tla_ui</token> necesita un código concreto para cada segmento de la canalización, el complemento y la aplicación host.</para> 
        <para> 
          <token>autoOutline</token>
        </para>
      </content>
      <sections>
        <section address="Contract">
          <title>Implementar el segmento de canalización del contrato</title>
          <content>
            <para>cuando un complemento es un <token>TLA&#2;tla_ui</token>, debe implementar el contrato para el complemento <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>. En el ejemplo, <codeInline>IWPFAddInContract</codeInline> implementa <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>, como se muestra en el código siguiente.</para>
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInContractAttribute

namespace Contracts
{
    /// &lt;summary&gt;
    /// Defines the services that an add-in will provide to a host application.
    /// In this case, the add-in is a UI.
    /// &lt;/summary&gt;
    [AddInContract]
    public interface IWPFAddInContract : INativeHandleContract {}
}</code>
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInContractAttribute

Namespace Contracts
    ''' &lt;summary&gt;
    ''' Defines the services that an add-in will provide to a host application.
    ''' In this case, the add-in is a UI.
    ''' &lt;/summary&gt;
    &lt;AddInContract&gt;
    Public Interface IWPFAddInContract
        Inherits INativeHandleContract
        Inherits IContract
    End Interface
End Namespace</code></content>
        </section>
        <section address="AddInViewPipeline">
          <title>Implementar el segmento de canalización de la vista de complemento</title>
          <content>
            <para>dado que el complemento se implementa como una subclase de la <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> tipo, la vista de complemento también debe crear subclases <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference>. El código siguiente muestra la vista de complemento del contrato, implementada como la <codeInline>WPFAddInView</codeInline> clase</para> 
            <code language="c#">using System.AddIn.Pipeline; // AddInBaseAttribute
using System.Windows.Controls; // UserControl

namespace AddInViews
{
    /// &lt;summary&gt;
    /// Defines the add-in's view of the contract.
    /// &lt;/summary&gt;
    [AddInBase]
    public class WPFAddInView : UserControl { }
}</code> 
          <code language="vb">Imports System.AddIn.Pipeline ' AddInBaseAttribute
Imports System.Windows.Controls ' UserControl

Namespace AddInViews
    ''' &lt;summary&gt;
    ''' Defines the add-in's view of the contract.
    ''' &lt;/summary&gt;
    &lt;AddInBase&gt;
    Public Class WPFAddInView
        Inherits UserControl
    End Class
End Namespace</code> 
            <para>En este caso, se deriva de la vista <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference>. Por consiguiente, el complemento <token>TLA&#2;tla_ui</token> también debe derivar de <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference>.</para>
          </content>
        </section>
        <section address="AddInSideAdapter">
          <title>Implementar el segmento de canalización del adaptador de Add-In-Side</title>
          <content>
            <para>mientras el contrato es un <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>, el complemento es un <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> (según se especifica en el segmento de canalización de la vista de complemento). Por lo tanto, la <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> deben convertirse a un <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador de conversión mediante una llamada a <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>, como se muestra en el código siguiente.</para> 
            <code language="c#">using System; // IntPtr
using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
using System.Security.Permissions;

using AddInViews; // WPFAddInView
using Contracts; // IWPFAddInContract

namespace AddInSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in's view of the contract to the add-in contract
    /// &lt;/summary&gt;
    [AddInAdapter]
    public class WPFAddIn_ViewToContractAddInSideAdapter : ContractBase, IWPFAddInContract
    {
        WPFAddInView wpfAddInView;

        public WPFAddIn_ViewToContractAddInSideAdapter(WPFAddInView wpfAddInView)
        {
            // Adapt the add-in view of the contract (WPFAddInView) 
            // to the contract (IWPFAddInContract)
            this.wpfAddInView = wpfAddInView;
        }

        /// &lt;summary&gt;
        /// ContractBase.QueryContract must be overridden to:
        /// * Safely return a window handle for an add-in UI to the host 
        ///   application's application.
        /// * Enable tabbing between host application UI and add-in UI, in the
        ///   "add-in is a UI" scenario.
        /// &lt;/summary&gt;
        public override IContract QueryContract(string contractIdentifier)
        {
            if (contractIdentifier.Equals(typeof(INativeHandleContract).AssemblyQualifiedName))
            {
                return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView);
            }

            return base.QueryContract(contractIdentifier);
        }

        /// &lt;summary&gt;
        /// GetHandle is called by the WPF add-in model from the host application's 
        /// application domain to to get the window handle for an add-in UI from the 
        /// add-in's application domain. GetHandle is called if a window handle isn't 
        /// returned by other means ie overriding ContractBase.QueryContract, 
        /// as shown above.
        /// NOTE: This method requires UnmanagedCodePermission to be called 
        ///       (full-trust by default), to prevent illegal window handle
        ///       access in partially trusted scenarios. If the add-in could
        ///       run in a partially trusted application domain 
        ///       (eg AddInSecurityLevel.Internet), you can safely return a window
        ///       handle by overriding ContractBase.QueryContract, as shown above.
        /// &lt;/summary&gt;
        [SecurityPermissionAttribute(SecurityAction.Demand, Flags = SecurityPermissionFlag.UnmanagedCode)]
        public IntPtr GetHandle()
        {
            return FrameworkElementAdapters.ViewToContractAdapter(this.wpfAddInView).GetHandle();
        }
    }
}</code> 
          <code language="vb">Imports System ' IntPtr
Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' AddInAdapterAttribute, FrameworkElementAdapters, ContractBase
Imports System.Security.Permissions

Imports AddInViews ' WPFAddInView
Imports Contracts ' IWPFAddInContract

Namespace AddInSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in's view of the contract to the add-in contract
    ''' &lt;/summary&gt;
    &lt;AddInAdapter&gt;
    Public Class WPFAddIn_ViewToContractAddInSideAdapter
        Inherits ContractBase
        Implements IWPFAddInContract

        Private wpfAddInView As WPFAddInView

        Public Sub New(ByVal wpfAddInView As WPFAddInView)
            ' Adapt the add-in view of the contract (WPFAddInView) 
            ' to the contract (IWPFAddInContract)
            Me.wpfAddInView = wpfAddInView
        End Sub

        ''' &lt;summary&gt;
        ''' ContractBase.QueryContract must be overridden to:
        ''' * Safely return a window handle for an add-in UI to the host 
        '''   application's application.
        ''' * Enable tabbing between host application UI and add-in UI, in the
        '''   "add-in is a UI" scenario.
        ''' &lt;/summary&gt;
        Public Overrides Function QueryContract(ByVal contractIdentifier As String) As IContract
            If contractIdentifier.Equals(GetType(INativeHandleContract).AssemblyQualifiedName) Then
                Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView)
            End If

            Return MyBase.QueryContract(contractIdentifier)
        End Function

        ''' &lt;summary&gt;
        ''' GetHandle is called by the WPF add-in model from the host application's 
        ''' application domain to to get the window handle for an add-in UI from the 
        ''' add-in's application domain. GetHandle is called if a window handle isn't 
        ''' returned by other means ie overriding ContractBase.QueryContract, 
        ''' as shown above.
        ''' NOTE: This method requires UnmanagedCodePermission to be called 
        '''       (full-trust by default), to prevent illegal window handle
        '''       access in partially trusted scenarios. If the add-in could
        '''       run in a partially trusted application domain 
        '''       (eg AddInSecurityLevel.Internet), you can safely return a window
        '''       handle by overriding ContractBase.QueryContract, as shown above.
        ''' &lt;/summary&gt;
        &lt;SecurityPermissionAttribute(SecurityAction.Demand, Flags:=SecurityPermissionFlag.UnmanagedCode)&gt;
        Public Function GetHandle() As IntPtr Implements INativeHandleContract.GetHandle
            Return FrameworkElementAdapters.ViewToContractAdapter(Me.wpfAddInView).GetHandle()
        End Function

    End Class
End Namespace</code> 
            <para>En el modelo de complemento donde un complemento devuelve un <token>TLA&#2;tla_ui</token> (consulte \<link xlink:href="57f274b7-4c66-4b72-92eb-81939a393776">Cómo: crear un complemento que devuelva una interfaz de usuario</link>), convertir el adaptador la <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> a una <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> llamando a <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference>. <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> también se debe llamar en este modelo, pero debe implementar un método desde el que se va a escribir el código para llamarlo. Para ello, reemplazar <codeEntityReference autoUpgrade="true">QueryContract</codeEntityReference> e implementar el código que llama a <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter(System.Windows.FrameworkElement)</codeEntityReference> si el código que llama a <codeEntityReference autoUpgrade="true">QueryContract</codeEntityReference> espera un <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>. En este caso, el llamador será el adaptador del host, que se trata en una subsección siguiente.</para>
            <alert class="note">
              <para> También necesitará reemplazar <codeEntityReference autoUpgrade="true">QueryContract</codeEntityReference> en este modelo para habilitar la tabulación entre la aplicación host <token>TLA&#2;tla_ui</token> y el complemento <token>TLA&#2;tla_ui</token>. Para obtener más información, vea "Limitaciones de complemento WPF" en \<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">WPF Add-Ins Overview</link>.</para> 
            </alert> 
            <para>Porque el adaptador de conversión implementa una interfaz que se deriva de <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>, también debe implementar <codeEntityReference autoUpgrade="true">M:System.AddIn.Contract.INativeHandleContract.GetHandle</codeEntityReference>, aunque esto se omite cuando <codeEntityReference autoUpgrade="true">QueryContract</codeEntityReference> se reemplaza.</para>
          </content>
        </section>
        <section address="HostViewPipeline">
          <title>Implementar el segmento de canalización de la vista de Host</title>
          <content>
            <para>en este modelo, la aplicación host normalmente espera que la vista de host sea un <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> subclase. El adaptador del host debe convertir la <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> a una <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> después de la <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> cruza el límite de aislamiento. Dado que la aplicación host no llama a un método la <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference>, la vista del host debe "return" la <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> por que lo contiene. Por lo tanto, la vista de host debe derivar de una subclase de <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> que pueden contener otros <token>TLA&#2;tla_ui #plural</token>, como <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference>. El código siguiente muestra la vista de host del contrato, implementada como la <codeInline>WPFAddInHostView</codeInline> clase.</para>
            <code language="c#">using System.Windows.Controls; // UserControl

namespace HostViews
{
    /// &lt;summary&gt;
    /// Defines the host's view of the add-in
    /// &lt;/summary&gt;
    public class WPFAddInHostView : UserControl { }
}</code>
          <code language="vb">Imports System.Windows.Controls ' UserControl

Namespace HostViews
    ''' &lt;summary&gt;
    ''' Defines the host's view of the add-in
    ''' &lt;/summary&gt;
    Public Class WPFAddInHostView
        Inherits UserControl
    End Class
End Namespace</code>
          </content>
        </section>
        <section address="HostSideAdapter">
          <title>Implementar el segmento de canalización del adaptador del Host</title>
          <content>
            <para>mientras el contrato es un <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference>, la aplicación host espera un <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference> (según se especifica en la vista del host). Por consiguiente, el <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> deben convertirse a un <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> después de cruzar el límite de aislamiento, antes de que se establece como el contenido de la vista de host (que deriva de <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference>).</para> 
            <para>Este trabajo lo realiza el adaptador del host, como se muestra en el código siguiente. </para> 
            <code language="c#">using System.AddIn.Contract; // INativeHandleContract
using System.AddIn.Pipeline; // HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
using System.Windows; // FrameworkElement

using Contracts; // IWPFAddInContract
using HostViews; // WPFAddInHostView

namespace HostSideAdapters
{
    /// &lt;summary&gt;
    /// Adapts the add-in contract to the host's view of the add-in
    /// &lt;/summary&gt;
    [HostAdapter]
    public class WPFAddIn_ContractToViewHostSideAdapter : WPFAddInHostView
    {
        IWPFAddInContract wpfAddInContract;
        ContractHandle wpfAddInContractHandle;

        public WPFAddIn_ContractToViewHostSideAdapter(IWPFAddInContract wpfAddInContract)
        {
            // Adapt the contract (IWPFAddInContract) to the host application's
            // view of the contract (WPFAddInHostView)
            this.wpfAddInContract = wpfAddInContract;

            // Prevent the reference to the contract from being released while the
            // host application uses the add-in
            this.wpfAddInContractHandle = new ContractHandle(wpfAddInContract);

            // Convert the INativeHandleContract for the add-in UI that was passed 
            // from the add-in side of the isolation boundary to a FrameworkElement
            string aqn = typeof(INativeHandleContract).AssemblyQualifiedName;
            INativeHandleContract inhc = (INativeHandleContract)wpfAddInContract.QueryContract(aqn);
            FrameworkElement fe = (FrameworkElement)FrameworkElementAdapters.ContractToViewAdapter(inhc);

            // Add FrameworkElement (which displays the UI provided by the add-in) as
            // content of the view (a UserControl)
            this.Content = fe;
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn.Contract ' INativeHandleContract
Imports System.AddIn.Pipeline ' HostAdapterAttribute, FrameworkElementAdapters, ContractHandle
Imports System.Windows ' FrameworkElement

Imports Contracts ' IWPFAddInContract
Imports HostViews ' WPFAddInHostView

Namespace HostSideAdapters
    ''' &lt;summary&gt;
    ''' Adapts the add-in contract to the host's view of the add-in
    ''' &lt;/summary&gt;
    &lt;HostAdapter&gt;
    Public Class WPFAddIn_ContractToViewHostSideAdapter
        Inherits WPFAddInHostView
        Private wpfAddInContract As IWPFAddInContract
        Private wpfAddInContractHandle As ContractHandle

        Public Sub New(ByVal wpfAddInContract As IWPFAddInContract)
            ' Adapt the contract (IWPFAddInContract) to the host application's
            ' view of the contract (WPFAddInHostView)
            Me.wpfAddInContract = wpfAddInContract

            ' Prevent the reference to the contract from being released while the
            ' host application uses the add-in
            Me.wpfAddInContractHandle = New ContractHandle(wpfAddInContract)

            ' Convert the INativeHandleContract for the add-in UI that was passed 
            ' from the add-in side of the isolation boundary to a FrameworkElement
            Dim aqn As String = GetType(INativeHandleContract).AssemblyQualifiedName
            Dim inhc As INativeHandleContract = CType(wpfAddInContract.QueryContract(aqn), INativeHandleContract)
            Dim fe As FrameworkElement = CType(FrameworkElementAdapters.ContractToViewAdapter(inhc), FrameworkElement)

            ' Add FrameworkElement (which displays the UI provided by the add-in) as
            ' content of the view (a UserControl)
            Me.Content = fe
        End Sub
    End Class
End Namespace</code> 
            <para>Como puede ver, el adaptador del host adquiere la <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> llamando el adaptador de complemento de conversión <codeEntityReference autoUpgrade="true">QueryContract</codeEntityReference> (método) (éste es el punto donde la <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> cruza el límite de aislamiento).</para> 
            <para>El adaptador del host, a continuación, convierte la <codeEntityReference autoUpgrade="true">INativeHandleContract</codeEntityReference> a una <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> llamando a <codeEntityReference autoUpgrade="true">M:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter(System.AddIn.Contract.INativeHandleContract)</codeEntityReference>. Por último, el <codeEntityReference autoUpgrade="true">FrameworkElement</codeEntityReference> se establece como el contenido de la vista del host.</para>
          </content>
        </section>
        <section address="AddIn">
          <title>Implementar el complemento</title>
          <content>
            <para>con el adaptador de complemento en el lado y la vista de complemento en su lugar, el complemento puede implementarse derivando de la vista de complemento, como se muestra en el siguiente código.</para> 
            <code language="xaml">&lt;addInViews:WPFAddInView
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:addInViews="clr-namespace:AddInViews;assembly=AddInViews"
    x:Class="WPFAddIn1.AddInUI"&gt;

    &lt;Grid&gt;
        &lt;Button Click="clickMeButton_Click" Content="Click Me!" /&gt;        
    &lt;/Grid&gt;

&lt;/addInViews:WPFAddInView&gt;</code> 
            <code language="c#">using System.AddIn; // AddInAttribute
using System.Windows; // MessageBox, RoutedEventArgs

using AddInViews; // WPFAddInView

namespace WPFAddIn1
{
    /// &lt;summary&gt;
    /// Implements the add-in by deriving from WPFAddInView
    /// &lt;/summary&gt;
    [AddIn("WPF Add-In 1")]
    public partial class AddInUI : WPFAddInView
    {
        public AddInUI()
        {
            InitializeComponent();
        }

        void clickMeButton_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Hello from WPFAddIn1");
        }
    }
}</code> 
          <code language="vb">Imports System.AddIn ' AddInAttribute
Imports System.Windows ' MessageBox, RoutedEventArgs

Imports AddInViews ' WPFAddInView

Namespace WPFAddIn1
    ''' &lt;summary&gt;
    ''' Implements the add-in by deriving from WPFAddInView
    ''' &lt;/summary&gt;
    &lt;AddIn("WPF Add-In 1")&gt;
    Partial Public Class AddInUI
        Inherits WPFAddInView
        Public Sub New()
            InitializeComponent()
        End Sub

        Private Sub clickMeButton_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
            MessageBox.Show("Hello from WPFAddIn1")
        End Sub
    End Class
End Namespace</code> 
            <para>En este ejemplo, puede ver una ventaja interesante de este modelo: los desarrolladores de complementos solamente necesitan implementar el complemento (ya que es el <token>TLA&#2;tla_ui</token> también), en lugar de una clase de complemento y un complemento <token>TLA&#2;tla_ui</token>.</para>
          </content>
        </section>
        <section address="HostApp">
          <title>Implementar la aplicación Host</title>
          <content>
            <para>con el adaptador del host y la vista de host creados, la aplicación host puede utilizar el <token>dnprdnshort</token> modelo de complementos para abrir la canalización y adquirir una vista de host del complemento. Estos pasos se muestran en el código siguiente. </para> 
            <code language="c#">// Get add-in pipeline folder (the folder in which this application was launched from)
string appPath = Environment.CurrentDirectory;

// Rebuild visual add-in pipeline
string[] warnings = AddInStore.Rebuild(appPath);
if (warnings.Length &gt; 0)
{
    string msg = "Could not rebuild pipeline:";
    foreach (string warning in warnings) msg += "\n" + warning;
    MessageBox.Show(msg);
    return;
}

// Activate add-in with Internet zone security isolation
Collection&lt;AddInToken&gt; addInTokens = AddInStore.FindAddIns(typeof(WPFAddInHostView), appPath);
AddInToken wpfAddInToken = addInTokens[0];
this.wpfAddInHostView = wpfAddInToken.Activate&lt;WPFAddInHostView&gt;(AddInSecurityLevel.Internet);

// Display add-in UI
this.addInUIHostGrid.Children.Add(this.wpfAddInHostView);</code> 
          <code language="vb">' Get add-in pipeline folder (the folder in which this application was launched from)
Dim appPath As String = Environment.CurrentDirectory

' Rebuild visual add-in pipeline
Dim warnings() As String = AddInStore.Rebuild(appPath)
If warnings.Length &gt; 0 Then
    Dim msg As String = "Could not rebuild pipeline:"
    For Each warning As String In warnings
        msg &amp;= vbLf &amp; warning
    Next warning
    MessageBox.Show(msg)
    Return
End If

' Activate add-in with Internet zone security isolation
Dim addInTokens As Collection(Of AddInToken) = AddInStore.FindAddIns(GetType(WPFAddInHostView), appPath)
Dim wpfAddInToken As AddInToken = addInTokens(0)
Me.wpfAddInHostView = wpfAddInToken.Activate(Of WPFAddInHostView)(AddInSecurityLevel.Internet)

' Display add-in UI
Me.addInUIHostGrid.Children.Add(Me.wpfAddInHostView)</code> 
            <para>La aplicación host usa típico <token>dnprdnshort</token> código de modelo de complementos para activar el complemento, lo que implícitamente devuelve la vista del host a la aplicación host. Posteriormente, la aplicación host muestra la vista del host (que es un <codeEntityReference autoUpgrade="true">UserControl</codeEntityReference>) desde una <codeEntityReference autoUpgrade="true">Grid</codeEntityReference>.</para> 
            <para>El código para procesar las interacciones con el complemento <token>TLA&#2;tla_ui</token> se ejecuta en el dominio de aplicación del complemento. Estas interacciones incluyen lo siguiente:</para>
            <list class="bullet">
              <listItem>
                <para>controla la <codeEntityReference autoUpgrade="true">Button</codeEntityReference> <codeEntityReference autoUpgrade="true">ButtonBase</codeEntityReference> eventos.</para> 
              </listItem> 
              <listItem> 
                <para>Que muestra la <codeEntityReference autoUpgrade="true">MessageBox</codeEntityReference>.</para> 
              </listItem> 
            </list> 
            <para>Esta actividad está completamente aislada de la aplicación host.</para>
          </content>
        </section>
      </sections>
    </legacy>
  </codeExample>
  <relatedTopics>
\<legacyLink xlink:href="8dd45b02-7218-40f9-857d-40d7b98b850b">Complementos y extensibilidad</legacyLink>
\<link xlink:href="00b4c776-29a8-4dba-b603-280a0cdc2ade">información general sobre complementos WPF</link>
</relatedTopics>
</developerHowToDocument>
