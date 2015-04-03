---
title: GridHyperLinkColumn/GridTemplateColumn
page_title: GridHyperLinkColumn/GridTemplateColumn | UI for ASP.NET AJAX Documentation
description: GridHyperLinkColumn/GridTemplateColumn
slug: grid/functionality/sorting/gridhyperlinkcolumn/gridtemplatecolumn
tags: gridhyperlinkcolumn/gridtemplatecolumn
published: True
position: 2
---

# GridHyperLinkColumn/GridTemplateColumn



## 

To enable sorting for __GridHyperLinkColumn__ and __GridTemplateColumn__, you need to set appropriate __SortExpression__ values for those columns.

* When using __GridHyperLinkColumn__, the __SortExpression__ value should match the __DataTextField__ property of the column.

* When using __GridTemplateColumn__, the __SortExpression__ value should match the data field you want to sort on (typically the field a control in the template is bound to).

````ASPNET
	  <telerik:RadGrid ID="RadGrid1" runat="server" DataSourceID="SqlDataSource1" AllowSorting="True"
	    Width="400px">
	    <MasterTableView AutoGenerateColumns="false" AllowSorting="true">
	      <Columns>
	        <telerik:GridHyperLinkColumn DataTextField="Country" NavigateUrl="http://www.telerik.com"
	          HeaderText="Country" SortExpression="Country" />
	        <telerik:GridTemplateColumn UniqueName="TemplateColumn" HeaderText="City" SortExpression="City">
	          <ItemTemplate>
	            <%# Eval("City") %>
	          </ItemTemplate>
	        </telerik:GridTemplateColumn>
	      </Columns>
	    </MasterTableView>
	  </telerik:RadGrid>
	  <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:NorthwindConnectionString %>"
	      SelectCommand="SELECT TOP 10 [Country], [City] FROM [Customers]">
	  </asp:SqlDataSource>
````



You can add a sort button to a template in the grid. When adding a sort button, set the __CommandName__ property to "Sort" and the sort expression as the __CommandArgument__ for the button. __RadGrid__ can then handle the sorting automatically when the user clicks the button.

````ASPNET
	  <telerik:GridTemplateColumn SortExpression="CompanyName">
	      <HeaderTemplate>
	        <asp:Button id="Button1" runat="server"
	           Text="GridTemplateColumn"
	           Title="Sort by CompanyName"
	           CommandName='Sort'
	           CommandArgument='CompanyName' />
	      </HeaderTemplate>
	      ...			
````

