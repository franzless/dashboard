<template>
    <div>        
        <v-layout justify-center>
            <v-flex xs8>
                <v-expansion-panel >
                    <v-expansion-panel-content v-for="(workflow,index) in workflows" :key="index">
                        <template v-slot:header>
                            <v-layout align-start>
                                <v-icon class="pr-5" color="green">lens</v-icon>
                            <div  @click="expand(workflow)">{{workflow}}</div>
                            </v-layout>                  
                    
                    
                    </template>
                    <v-card>
                        <v-card-text>
                            <v-data-table
                                :headers="headers"
                                v-if="items.length>0"
                                :items="items"
                                hide-actions
                                class="elevation-1"                                
                                pagination.sync="pagination"
                                item-key="id"
                                loading="true"
                                >
                                 <template slot="items" slot-scope="props">                                    
                                    <td>{{ props.item.IS_GLOBALPID}}</td>
                                    <td>{{ props.item.IS_WORKFLOWID}}</td>
                                    <td>{{ props.item.IS_STARTTIME }}</td>
                                    <td>{{ props.item.IS_ENDTIME }}</td>
                                    <td>{{ props.item.IS_USERDEFINED1 }}</td>
                                    <td><v-icon>check_circle</v-icon>
                                        <v-icon>bug_report</v-icon></td>
                                </template>
                            </v-data-table>
                        </v-card-text>
                    </v-card>
                    </v-expansion-panel-content>
                 </v-expansion-panel> 

            </v-flex>
        </v-layout>
        
        
    </div>
</template>
<script>

export default {
    data(){
        return{
            headers:[{text:'GlobalProcessID',value:'IS_GLOBALPID'},{text:'ProcessID',value:'IS_WORKFLOWID'},
            {text:'Start',value:'IS_STARTTIME'},{text:'Ende',value:'IS_ENDTIME'},{text:'Payload',value:'IS_USERDEFINED1'},{text:'Actions'}] ,           
            items:[{IS_GLOBALPID:'32325',IS_WORKFLOWID:435435,IS_STARTTIME:234234,IS_ENDTIME:832434,IS_USERDEFINED1:'<test></test>ldsfjldsfjodsjfsdlhfldshflisdhflihsdfhlidshflidshflihdsf',IS_WORKFLOWNAME:'A_CMC_FTS_TCP_SENDER'}],
            workflows:['A_CMC_AMGTrace_DB','A_CMC_AMGTrace_Listener','A_CMC_ATLASCOPCO_TCP-Listener_Ergebnistelegramm','A_CMC_ATLASCOPCO_TCP-Listener_Ergebnistelegramm', 
                      'A_CMC_AMGTrace_DB',
                      'A_CMC_ATLASCOPCO_TCP-Sender_Schrauberanforderung',
                      'A_CMC_FTS_TCP_Sender',
                      'A_CMC_SafeLog_Listener',
                      'A_CMC_SafeLog_Sender',
                      'A_CMC_SAP_Listener',
                      'A_CMC_SAP_Sender',
                      'A_CMC_UBISENSE_Listener',
                      'B_CMC_AMGTrace_Materialbild_Writer',
                      'B_CMC_AMGTrace_Reader',
                      'B_CMC_AMGTrace_Router',
                      'B_CMC_AMGTrace_writer',
                      'B_CMC_AMGTraceTransformation',
                      'B_CMC_FTSTransformation',
                      'B_CMC_SafeLog_Router',
                      'B_CMC_UBISENSE_ROUTER',
                      'B_CMC_UBISENSE_ROUTER_S1',
                      'B_CMC_UBISENSE_ROUTER_DB'

                        ]
            
            }},
            methods:{
                expand(wf){
                    this.items.filter(wf=>wf.IS_WORKFLOWNAME==wf)
                    console.log(this.items)
                }
            }}

</script>    