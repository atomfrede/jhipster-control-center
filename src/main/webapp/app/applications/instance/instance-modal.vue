<template>
    <div class="modal-body pad">
        <div v-if="selectedInstance && selectedInstanceRoute">
            <div class="table">
                <table class="table table-bordered">
                    <tbody>
                        <tr>
                            <td class="text-left align-middle">
                                <div>URI</div>
                            </td>
                            <td class="text-left">
                                <a :href="selectedInstance.uri" target="_blank">
                                    {{selectedInstance.uri}}
                                </a>
                            </td>
                        </tr>
                        <tr>
                            <td class="text-left">
                                Port
                            </td>
                            <td class="text-left">
                                {{selectedInstance.port}}
                            </td>
                        </tr>
                        <tr>
                            <td class="text-left">
                                Secure
                            </td>
                            <td class="text-left">
                                {{selectedInstance.secure}}
                            </td>
                        </tr>
                        <tr>
                            <td class="text-left">
                                Route
                            </td>
                            <td class="text-left">
                                <span class="badge badge-pill badge-info">
                                    {{selectedInstanceRoute}}
                                </span>
                            </td>
                        </tr>
                        <tr v-if="activeProfiles">
                            <td class="text-left">
                                Active Profiles
                            </td>
                            <td class="text-left align-middle">
                                <span v-for="content in activeProfiles.activeProfiles" v-bind:key="content" class="badge badge-pill badge-success mr-2">
                                    {{ content }}
                                </span>
                            </td>
                        </tr>
                        <tr v-if="selectedInstance.metadata && selectedInstance.metadata.profile">
                            <td class="text-left">
                                Profile
                            </td>
                            <td class="text-left">
                                <span class="badge badge-pill badge-primary">{{selectedInstance.metadata.profile}}</span>
                            </td>
                        </tr>
                        <tr v-if="selectedInstance.metadata && selectedInstance.metadata.version">
                            <td class="text-left">
                                Version
                            </td>
                            <td class="text-left">
                                <span class="badge badge-pill badge-primary">{{selectedInstance.metadata.version}}</span>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        <div v-if="selectedInstanceRoute && selectedInstanceRoute.error">
            <h4>Error</h4>
            <pre>{{selectedInstanceRoute.error}}</pre>
        </div>
    </div>
</template>

<script lang="ts" src="./instance-modal.component.ts">
</script>
