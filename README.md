# bstravellrp
Travel application with annotations (Fiori elements)

ZATS_MDE_FE_TRAVEL
@Metadata.layer: #CUSTOMER
@UI.headerInfo:{
    typeNamePlural: 'Travels',
    typeName: 'Travel',
    title: { type: #STANDARD,
             iconUrl: 'sap-icon://flight',
             value: 'TravelId' },
    description: { type: #STANDARD,
                   value: 'Description' }
}
annotate view ZATS_C_FE_TRAVEL
    with 
{

    @UI.facet: [{ 
        id: 'TravelPrice',
        purpose: #HEADER,
        type: #DATAPOINT_REFERENCE,
        position: 10,
        targetQualifier: 'PriceInfo'
     },
     {
        id: 'StatusInfo',
        purpose: #HEADER,
        type: #DATAPOINT_REFERENCE,
        position: 20,
        targetQualifier: 'StatusInfo'
     },
     {
       id: 'facetCollection',
       label: 'General information',
       type: #COLLECTION,
       position: 10 
     },
     {
       label: 'General',
       id: 'Travel',
       type: #IDENTIFICATION_REFERENCE,
       purpose: #STANDARD,
       parentId: 'facetCollection',
       position: 10
      },
      { 
       label: 'Flight dates',
       id: 'DatesData',
       purpose: #STANDARD,
       type: #FIELDGROUP_REFERENCE,
       parentId: 'facetCollection',
       position: 20,
       targetQualifier: 'DateFields'
      },
      { 
       id: 'PriceData',
       label: 'Price info',
       purpose: #STANDARD,
       type: #FIELDGROUP_REFERENCE,
       parentId: 'facetCollection',
       position: 30,
       targetQualifier: 'PriceFields'
      },
      { 
       id: 'BookingData',
       label: 'Bookings',
       purpose: #STANDARD,
       type: #LINEITEM_REFERENCE,
       position: 20,
       targetElement: '_BOOKING'
      }
     ]

    @UI.lineItem: [{ position: 10 }]
    @EndUserText.label: 'Travel ID'
    TravelId;
    @UI.identification: [{ position: 10 }]
    Description;
    @UI.lineItem: [{ position: 20 }]
    @UI.selectionField: [{ position: 10 }]
    @UI.identification: [{ position: 20 }]
    AgencyId;
    @UI.lineItem: [{ position: 30 }]
    AgencyName;
    @UI.lineItem: [{ position: 40 }]
    @UI.selectionField: [{ position: 20 }]
    @UI.identification: [{ position: 30 }]
    CustomerId;
    @UI.lineItem: [{ position: 50 }]
    @UI.fieldGroup: [{ qualifier: 'DateFields', position: 10 }]
    BeginDate;
    @UI.lineItem: [{ position: 60 }]
    @UI.fieldGroup: [{ qualifier: 'DateFields', position: 20 }]
    EndDate;
    @UI.lineItem: [{ position: 70 }]
    BookingFee;
    @UI.lineItem: [{ position: 80 }]
    @UI.dataPoint: { qualifier: 'PriceInfo', title: 'Price'}
    @UI.fieldGroup: [{ qualifier: 'PriceFields', position: 10 }]
    TotalPrice;
    @UI.lineItem: [{ position: 90, importance: #HIGH }]
    @UI.selectionField: [{ position: 30 }]
    @UI.dataPoint: { qualifier: 'StatusInfo', title: 'Status'}
    @UI.fieldGroup: [{ qualifier: 'PriceFields', position: 10 }]
    OverallStatus;
    @UI.lineItem: [{ position: 100 }]
    LocalLastChangedAt;
}
****************************************************************
ZATS_MDE_FE_BOOKING

@Metadata.layer: #CUSTOMER

annotate view ZATS_C_FE_BOOKING
    with 
{
    @UI.lineItem: [{ position: 10 }]
    BookingId;
    @UI.lineItem: [{ position: 20 }]
    BookingDate;
    @UI.lineItem: [{ position: 30 }]
    CustomerId;
    @UI.lineItem: [{ position: 40 }]
    CarrierId;
    @UI.lineItem: [{ position: 50 }]
    ConnectionId;
    @UI.lineItem: [{ position: 60 }]
    FlightDate;
    @UI.lineItem: [{ position: 70 }]
    FlightPrice;
    
}
****************************************************************
