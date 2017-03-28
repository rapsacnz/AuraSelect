# Select
A lightning Select Component that can be initialized with a selected item (no, the built-in one can't do that)

To use include in your component like this:

    <c:Select value="{!v.selectedOption}" options="{!v.options}" selectChange="{!c.handleSelectChange}" />
    
Option and values are respectively a `String` and a standard Salesforce `SelectList` array

    <aura:attribute name="selectedOption" type="String" />
    <aura:attribute name="options" type="SelectOption[]" />
    
To handle the selectChange event, do this:

    handleSelectChange: function(component, event, helper) {
      var val = event.getParam("data");
      helper.doSomething(component, val);
    },

There is a "DataChange" event dependency in this component - get it from the DatePicker component.
