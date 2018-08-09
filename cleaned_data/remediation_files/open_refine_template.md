# OpenRefine Template for Knoxville Garden Slides (migration)

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="local">{{cells["adminDB"].value}}</identifier>
{{if(isBlank(cells['PID'].value), '', '<identifier type="pid">' + cells['PID'].value + '</identifier>')}}
<identifier type="slide number">{{cells['slide_number'].value'}}</identifier>
<identifier type="film number">{{cells['film_new_number'].value}}</identifier>
{{if(isBlank(cells['identifier_spc'].value), '', '<identifier type="spc">' + cells['identifier_spc'].value + '</identifier>')}}
{{if(isBlank(cells["supplied_title"].value), '', '<titleInfo supplied="yes"><title>' + cells["supplied_title"].value + '</title></titleInfo>')}}
{{if(isBlank(cells["title_transcribed"].value), '', '<titleInfo><title>' + cells["title_transcribed"].value + '</title></titleInfo>')}}
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
{{'<originInfo><dateCreated qualifier="inferred">' + cells['dateCreated'].value + '</dateCreated><dateCreated encoding="edtf" point="start" qualifier="inferred" keyDate="yes">' + cells['dateStart'].value + '</dateCreated><dateCreated encoding="edtf" point="end" qualifier="inferred">' + cells['dateEnd'].value + '</dateCreated></originInfo>'}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><extent>{{cells['extent'].value}}</extent><internetMediaType>image/jp2</internetMediaType></physicalDescription>
{{if(isBlank(cells['creator'].value), '', '<name'+ if(isBlank(cells['creator_URI'].value), '', ' valueURI="' + cells['creator_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['creator'].value + '</namePart>' + if(isBlank(cells['role'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['role_URI'].value + '">' + cells['role'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['subject_all'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_all_URI'].value + '"><topic>' + cells['subject_all'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject4_URI'].value + '"><topic>' + cells['subject4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject5'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject5_URI'].value + '"><topic>' + cells['subject5'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_geo'].value), '', '<subject authority="' + cells['subject_geo_authority'].value + '" valueURI="' + cells['subject_geo_URI'].value + '"><geographic>' + cells['subject_geo'].value + '</geographic><cartographics><coordinates>' + cells['coordinates'].value + '</coordinates></cartographics></subject>')}}
<note>{{cells['note'].value}}</note>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>
<relatedItem displayLabel="Collection" type="host"><titleInfo><title>{{cells['archival_collection'].value}}</title></titleInfo><identifier>{{cells['collection_identifier'].value}}</identifier><location><url>{{cells['ARK'].value}}</url></location></relatedItem>
<location><physicalLocation valueURI="{{cells['repository_URI'].value}}">{{cells['repository'].value}}</physicalLocation></location>
<recordInfo><recordContentSource valueURI="{{cells['recordsource_URI'].value}}">{{cells['record_source'].value}}</recordContentSource><languageOfCataloging>
<languageTerm type="text" authority="iso639-2b">English</languageTerm>
</languageOfCataloging></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```