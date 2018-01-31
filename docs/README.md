#### Diadem Assessment

#### Version:

1.1.0

23-Feb-2017

#### TemplateID:
`DiADeM Assessment.v1`


#### MARKED-UP Composition(FLAT JSON) for POST/PUT /composition:

To create or update a composition for a single item via the /composition Ehrscape API call.

NOTE!!!! - this is not valid JSON - it will croak if you try to submit it to Ehrscape. See below for the RAW non-marked up version.

```
{
    //HARDWIRED
    "ctx/language": "en",

    //HARDWIRED
    "ctx/territory": "GB",

    //HARDWIRED - just for any internal Ids
    "ctx/id_namespace": "uk.org.diadem",

    //HARDWIRED
    "ctx/id_scheme": "uk.org.diadem",

    // prep_interviewerName
    "ctx/composer_name": "Silvia Blake",

    // prep_interview_DateTime
    "ctx/time": "2017-02-23T13:37:16.380Z",

    //prep_locationName
    "ctx/health_care_facility|name": "Woodlands Nursing Home",

    //prep_locationType
    // Allowed Values
    // local::at0044::Nursing Home
    // local::at0045::Residential Care Home
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type|code": "at0044",

    // HARDWIRED
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0/target|terminology": "SNOMED-CT",

    //if local::at0044::Nursing Home is selected
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0/target|code": "160733006",
    // else if local::at0045::Residential Care Home is selected
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0/target|code": "257688003",

    //if local::at0044::Nursing Home is selected
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1/target|terminology": "READ",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1/target|code": "13F61",

    //if local::at0044::Nursing Home is selected
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2/target|terminology": "CTV3",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2/target|code": "XalmT",

    //HARDWIRED
    "diadem_assessment/consent/assessment": "Consent for DiADeM Assessment",

    //HARDWIRED - means Action state is complete
    "diadem_assessment/consent/ism_transition/current_state|code": "245",

    //HARDWIRED - means Consent provided and consenting process complete
    "diadem_assessment/consent/ism_transition/careflow_step|code": "at0015",

    //HARDWIRED
    "diadem_assessment/consent/_other_participation:0|function": "Source of consent",
    //HARDWIRED
    "diadem_assessment/consent/_other_participation:0|mode": "not specified",

    // prep_sourceOfConsentString
    // Allowed values
    // one of: "Please Select", "Patient", "Patient's Next of Kin", "Patient's close relative", "Patient's Care Home staff member"
    "diadem_assessment/consent/_other_participation:0|name": "Patient's Next of Kin",

    //post_chosen_clinician
    "diadem_assessment/gp/gp_details/person_name/gp_name": "Dr Dai Snodgrass",

    //post_chosen_clinician_email
    "diadem_assessment/gp/gp_details/comms_contact_details/gp_email": "dave@shangrila.io",

    //prep_informantName
    "diadem_assessment/informant/informant_details/person_name/informant_name": "Ms Sneaky",
    "diadem_assessment/informant/informant_details/telecom_details/informant_contact_number": "mobile 01345 56789",

    //prep_relationshipToPatient
    "diadem_assessment/informant/relationship": "Carer",

    // diadem_q2_functionalImpairment
    // Allowed Values
    //local::at0006::True
    //local::at0005::False
    "diadem_assessment/yhscn_-_diadem_assessment/functional_impairment|code": "at0005",

    // diadem_q2_cognitiveImpairment
    // Allowed Values
    // local::at0039::True
    // local::at0040::False
    "diadem_assessment/yhscn_-_diadem_assessment/cognitive_impairment|code": "at0040",

    // diadem_q3_corroboratingHistory
    // Allowed Values
    // local::at0011::True
    // local::at0010::False
    "diadem_assessment/yhscn_-_diadem_assessment/corroborating_history|code": "at0011",

    // diadem_q4_bloodResultsAvailable
    // Allowed Values
    // local::at0032::Yes
    // local::at0033::No
    // local::at0034::Not appropriate
    // local::at0046::Not available at assessment
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available|code": "at0034",
    // All HARDWIRED
    // only add these code bindings if local::at0034::Not appropriate
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0/target|terminology": "CTV3",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0/target|code": "XaZOq",

    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1/target|terminology": "SNOMED-CT",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1/target|code": "839621000000101",

    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2/target|terminology": "READ",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2/target|code": "41M..",

    // diadem_q4_bloodResultsAvailableAtAssessmentString AND diadem_q4_considerBloodTest
    // Depending on values of above populate "".../blood_test_recommendation" with
    // "Please check before confirming diagnosis of dementia"
    // OR
    // "Consider Referral for Blood Test"
    "diadem_assessment/yhscn_-_diadem_assessment/blood_test_recommendation": "Consider Referral for Blood Test",

    //diadem_q4_intracranialPathologySuspected
    // Allowed Values
    // local::at0036::Yes
    // local::at0037::No
    "diadem_assessment/yhscn_-_diadem_assessment/intracranial_pathology_suspected|code": "at0037",

    //diadem_q4_considerBrainScan
    "diadem_assessment/yhscn_-_diadem_assessment/brain_scan_recommendation": "Consider Referral for Brain Scan",

    //diadem_q4_investigations
    // Allowed Values
    // local::at0012::True
    // local::at0013::False
    "diadem_assessment/yhscn_-_diadem_assessment/investigations|code": "at0012",

    //diadem_q5_exclusionCriteria
    "diadem_assessment/yhscn_-_diadem_assessment/exclusion_criteria|code": "at0015",
    // Allowed Values
    // local::at0014::True
    // local::at0015::False

    //diadem_result
    // Allowed Values
    // local::at0029::Diagnosis of dementia indicated
    // local::at0030::Diagnosis of dementia not indicated,
    "diadem_assessment/yhscn_-_diadem_assessment/interpretation|code": "at0030",

    // 6CIT_q1_whatYear
    // Allowed Values
    // local::at0005::Correct
    // local::at0006::Incorrect
    "diadem_assessment/a6_cit_assessment/what_year|code": "at0006",

    // 6CIT_q2_whatMonth
    // Allowed Values
    // local::at0008::Correct
    // local::at0009::Incorrect
    "diadem_assessment/a6_cit_assessment/what_month|code": "at0008",

    // 6CIT_q4_whatTime
    // Allowed Values
    // local::at0011::Correct
    // local::at0012::Incorrect
    "diadem_assessment/a6_cit_assessment/about_what_time|code": "at0012",

    // 6CIT_q5_countBackwards
    // Allowed Values
    // local::at0014::No errors
    // local::at0015::1 error
    // local::at0016::More than 1 error
    "diadem_assessment/a6_cit_assessment/count_backwards|code": "at0014",

    // 6CIT_q6_monthsInReverse
    // Allowed Values
    // local::at0018::No errors
    // local::at0019::1 error
    // local::at0020::More than 1 error
    "diadem_assessment/a6_cit_assessment/months_in_reverse|code": "at0020",

    // 6CIT_q7_whatAddress
    // Allowed Values
    // local::at0022::No errors
    // local::at0023::1 error
    // local::at0024::2 errors
    // local::at0025::3 errors
    // local::at0026::4 errors
    // local::at0027::5 errors
    "diadem_assessment/a6_cit_assessment/repeat_address_phrase|code": "at0026",

    // 6CIT_total_score
    "diadem_assessment/a6_cit_assessment/total_score": 17,

    // 6CIT_summary
    // Allowed Values
    // local::at0034::Cognitive impairment indicated
    // local::at0035::Impairment NOT indicated
    "diadem_assessment/a6_cit_assessment/interpretation|code": "at0034",

    // GP1_q1_date
    // Allowed Values
    // local::at0009::Incorrect
    // local::at0010::Correct
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/date|code": "at0009",

    // GP1_q2_numbers
    // Allowed values
    // local::at0012::Incorrect
    // local::at0013::Correct
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/clock_drawing_-_all_numbers|code": "at0013",

    // GP1_q3_time
    // Allowed Values
    // local::at0015::Incorrect
    // local::at0016::Correct
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/clock_drawing_-_specific_time|code": "at0016",

    // GP1_q4_news
    // Allowed Values
    // local::at0018::Incorrect
    // local::at0019::Correct
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/information|code": "at0019",

    // GP1_q5_address
    // Allowed Values
    // local::at0021::None correct
    // local::at0022::1 correct
    // local::at0067::2 correct
    // local::at0068::3 correct
    // local::at0069::4 correct
    // local::at0070::5 correct
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/recall_name_and_address_phrase|code": "at0021",

    // GP1_total_score
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/total_score": 8,

    // GP2_q1_remembering
    // Allowed Values
    // local::at0040::Yes
    // local::at0041::No
    // local::at0042::Don't know
    // local::at0071::Not applicable
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/trouble_remembering|code": "at0041",

    // GP2_q2_recalling
    // Allowed Values
    // local::at0044::Yes
    // local::at0045::No
    // local::at0046::Don't know
    // local::at0072::Not applicable
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/trouble_recalling_conversations|code": "at0044",

    // GP2_q3_words
    // Allowed Values
    // local::at0048::Yes
    // local::at0049::No
    // local::at0050::Don't know
    // local::at0073::Not applicable    
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/difficulty_finding_right_words_or_using_wrong_words|code": "at0049",

    // GP2_q4_money
    // Allowed Values
    // local::at0052::Yes
    // local::at0053::No
    // local::at0054::Don't know
    // local::at0055::Not applicable
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/less_able_to_manage_money|code": "at0054",

    // GP2_q5_medication
    // Allowed Values
    // local::at0057::Yes
    // local::at0058::No
    // local::at0059::Don't know
    // local::at0060::Not applicable
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/less_able_to_manage_medication|code": "at0058",

    // GP2_q6_transport
    // Allowed Values
    // local::at0062::Yes
    // local::at0063::No
    // local::at0064::Don't know
    // local::at0065::Not applicable
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/needs_more_assistance_with_transport|code": "at0062",

    // GP2_total_score
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/total_score": 0,

    // GPCOG_overall_interpretation
    // Allowed Values
    // local::at0075::Impairment indicated
    // local::at0076::Impairment NOT indicated,
    "diadem_assessment/gpcog_screening_test/overall_interpretation|code": "at0076"

  // Only add mappings if local::at0075::Impairment indicated
    // All HARDWIRED
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0/target|terminology": "SNOMED-CT",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0/target|code": "52448006",

    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1/target|terminology": "READ",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1/target|code": "Eu02z",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2/target|terminology": "CTV3",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2/target|code": "XE1Z6",

    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3/target|terminology": "ICD10_1998",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3/target|code": "F03"
}

```

#### RAW Composition(FLAT JSON) for POST/PUT /composition:

To create or update a composition for a single item via the /composition Ehrscape API call.

```
{
    "ctx/language": "en",
    "ctx/territory": "GB",
    "ctx/id_namespace": "uk.org.diadem",
    "ctx/id_scheme": "uk.org.diadem",
    "ctx/composer_name": "ObiWan",
    "ctx/time": "2014-02-23T13:37:16.380Z",
    "ctx/health_care_facility|name": "Woodlands Nursing Home",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type|code": "at0044",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0/target|terminology": "SNOMED-CT",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:0/target|code": "21794005",  
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1/target|terminology": "READ",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:1/target|code": "13F61",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2/target|terminology": "CTV3",
    "diadem_assessment/yhscn_-_diadem_assessment/assessment_location_type/_mapping:2/target|code": "XalmT",
    "diadem_assessment/consent/assessment": "Consent for DiADeM Assessment",
    "diadem_assessment/consent/ism_transition/current_state|code": "245",
    "diadem_assessment/consent/ism_transition/careflow_step|code": "at0015",
    "diadem_assessment/consent/_other_participation:0|function": "Source of consent",
    "diadem_assessment/consent/_other_participation:0|mode": "not specified",
    "diadem_assessment/consent/_other_participation:0|name": "Patient's close relative",
    "diadem_assessment/gp/gp_details/person_name/gp_name": "Dr Dai Snodgrass",
    "diadem_assessment/gp/gp_details/comms_contact_details/gp_email": "dave@shangrila.io",
    "diadem_assessment/informant/informant_details/person_name/informant_name": "Ms Sneaky",
    "diadem_assessment/informant/informant_details/telecom_details/informant_contact_number": "mobile 01345 56789",
    "diadem_assessment/informant/relationship": "Carer",
    "diadem_assessment/yhscn_-_diadem_assessment/functional_impairment|code": "at0005",
    "diadem_assessment/yhscn_-_diadem_assessment/cognitive_impairment|code": "at0040",
    "diadem_assessment/yhscn_-_diadem_assessment/corroborating_history|code": "at0011",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available|code": "at0034",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0/target|terminology": "CTV3",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:0/target|code": "XaZOq",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1/target|terminology": "SNOMED-CT",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:1/target|code": "839621000000101",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2|match": "=",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2/target|terminology": "READ",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_tests_available/_mapping:2/target|code": "41M..",
    "diadem_assessment/yhscn_-_diadem_assessment/blood_test_recommendation": "Consider Referral for Blood Test",
    "diadem_assessment/yhscn_-_diadem_assessment/intracranial_pathology_suspected|code": "at0037",
    "diadem_assessment/yhscn_-_diadem_assessment/brain_scan_recommendation": "Consider Referral for Brain Scan",
    "diadem_assessment/yhscn_-_diadem_assessment/investigations|code": "at0012",
    "diadem_assessment/yhscn_-_diadem_assessment/exclusion_criteria|code": "at0015",
    "diadem_assessment/yhscn_-_diadem_assessment/interpretation|code": "at0030",
    "diadem_assessment/a6_cit_assessment/what_year|code": "at0006",
    "diadem_assessment/a6_cit_assessment/what_month|code": "at0008",
    "diadem_assessment/a6_cit_assessment/about_what_time|code": "at0012",
    "diadem_assessment/a6_cit_assessment/count_backwards|code": "at0014",
    "diadem_assessment/a6_cit_assessment/months_in_reverse|code": "at0020",
    "diadem_assessment/a6_cit_assessment/repeat_address_phrase|code": "at0026",
    "diadem_assessment/a6_cit_assessment/total_score": 17,
    "diadem_assessment/a6_cit_assessment/interpretation|code": "at0034",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/date|code": "at0009",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/clock_drawing_-_all_numbers|code": "at0013",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/clock_drawing_-_specific_time|code": "at0016",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/information|code": "at0019",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/recall_name_and_address_phrase|code": "at0021",
    "diadem_assessment/gpcog_screening_test/step_1_patient_examination/total_score": 8,
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/trouble_remembering|code": "at0041",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/trouble_recalling_conversations|code": "at0044",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/difficulty_finding_right_words_or_using_wrong_words|code": "at0049",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/less_able_to_manage_money|code": "at0054",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/less_able_to_manage_medication|code": "at0058",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/needs_more_assistance_with_transport|code": "at0062",
    "diadem_assessment/gpcog_screening_test/step_2_informant_interview/total_score": 4,
    "diadem_assessment/gpcog_screening_test/overall_interpretation|code": "at0075",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0/target|terminology": "SNOMED-CT",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:0/target|code": "52448006",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1/target|terminology": "READ",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:1/target|code": "Eu02z",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2/target|terminology": "CTV3",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:2/target|code": "XE1Z6",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3|match": "=",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3/target|terminology": "ICD10_1998",
    "diadem_assessment/gpcog_screening_test/overall_interpretation/_mapping:3/target|code": "F03"
}
```
#### Notes:

SNOMED mappings

at0044::Nursing Home	at0045::Residential Care Home

Environment	SCTID: 160733006 Nursing or other home	SCTID: 257688003 Residential home
Finding	SCTID: 185218006 Seen in nursing home	SCTID: 275691001 Seen in old people's home
Finding	SCTID: 160734000 Lives in nursing home	SCTID: 248171000000108 Lives in care home
Record artefact	SCTID: 24751000000101 Nursing home visit note	SCTID: 24631000000103 Residential home visit note
