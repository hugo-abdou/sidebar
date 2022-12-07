<template>
    <div
        :class="[
            'bg-white/50 backdrop-blur-sm  duration-150 rounded-2xl py-5 relative',
            isOpen ? 'w-72' : 'w-28',
        ]"
    >
        <!-- @mouseenter="isOpen = true"
        @mouseleave="isOpen = false" -->
        <button
            @click="isOpen = !isOpen"
            class="bg-white/50 backdrop-blur-md py-1.5 rounded-r-md text-gray-400 absolute -right-4 top-5"
        >
            <svg
                xmlns="http://www.w3.org/2000/svg"
                width="1em"
                height="1em"
                preserveAspectRatio="xMidYMid meet"
                viewBox="0 0 24 24"
            >
                <path
                    fill="currentColor"
                    d="M15.125 21.1L6.7 12.7q-.15-.15-.212-.325q-.063-.175-.063-.375t.063-.375q.062-.175.212-.325l8.425-8.425q.35-.35.875-.35t.9.375q.375.375.375.875t-.375.875L9.55 12l7.35 7.35q.35.35.35.862q0 .513-.375.888t-.875.375q-.5 0-.875-.375Z"
                />
            </svg>
        </button>
        <div class="overflow-auto scroll h-[calc(100vh-60px)]">
            <div class="px-8 py-3">
                <a class="block">
                    <div class="flex items-center">
                        <img
                            class="inline-block ring-4 ring-white h-11 w-11 rounded-full"
                            src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                            alt=""
                        />
                        <div class="ml-3 whitespace-nowrap overflow-hidden">
                            <p
                                class="text-xs font-medium text-gray-500 group-hover:text-gray-700"
                            >
                                View profile
                            </p>
                            <p
                                class="text-lg font-bold text-gray-700 group-hover:text-gray-900"
                            >
                                Tom Cook
                            </p>
                        </div>
                    </div>
                </a>
            </div>
            <div class="px-6">
                <span
                    class="inline-block border-b border-gray-400/50 w-full"
                ></span>
            </div>
            <div class="px-6 pt-3">
                <span class="text-xs font-semibold text-gray-500">
                    Menu: 6
                </span>
            </div>
            <ul :class="[isOpen ? 'px-3' : 'px-8', 'space-y-1']">
                <SideBarLink
                    icon="ic:round-dashboard-customize"
                    name="Dashboard"
                />
                <SideBarLink
                    icon="ph:folder-open-fill"
                    name="My project task"
                />
                <SideBarLink icon="mdi:calendar-text" name="Calendar" />
                <SideBarLink icon="mingcute:mail-send-fill" name="Mail" />
                <SideBarLink icon="mdi:bell-notification" name="Notification" />
                <SideBarLink icon="majesticons:basket-2" name="Sales" />
            </ul>
            <div class="px-6">
                <span
                    class="inline-block border-b border-gray-400/50 w-full"
                ></span>
            </div>
            <div class="px-6 py-3 whitespace-nowrap">
                <span class="text-xs font-semibold text-gray-500">
                    Services: 3
                </span>
                <ul class="bg-white p-1.5 mt-2 rounded-2xl">
                    <SideBarLink
                        iconBg
                        hoverVarient="gray"
                        name="Jira software"
                        icon="la:jira"
                    />
                    <SideBarLink
                        iconBg
                        hoverVarient="gray"
                        name="Slack"
                        icon="logos:slack-icon"
                    />
                    <SideBarLink
                        iconBg
                        hoverVarient="gray"
                        name="Intercom"
                        icon="logos:intercom-icon"
                    />
                    <SideBarLink
                        iconBg
                        hoverVarient="gray"
                        name="Add new plugin"
                        icon="ic:round-plus"
                    />
                </ul>
            </div>
            <div class="px-6 whitespace-nowrap">
                <span class="text-xs font-semibold text-gray-500">
                    Services: 3
                </span>
                <ul
                    :class="[
                        'bg-white max-w-full scroll overflow-auto p-1.5 mt-2 rounded-2xl',
                        isOpen ? 'flex' : '',
                    ]"
                >
                    <SideBarLink
                        iconClass="w-6 h-6 px-0.5"
                        icon="majesticons:basket-2"
                    />
                    <SideBarLink
                        iconClass="w-6 h-6 px-0.5"
                        icon="majesticons:basket-2"
                    />
                    <SideBarLink
                        iconClass="w-6 h-6 px-0.5"
                        icon="majesticons:basket-2"
                    />
                    <SideBarLink
                        iconClass="w-6 h-6 px-0.5"
                        icon="majesticons:basket-2"
                    />
                </ul>
                <div
                    :class="[
                        'max-w-full scroll overflow-auto mt-2 rounded-2xl flex flex-col items-center ',
                        isOpen && 'p-2 py-4 bg-white',
                    ]"
                >
                    <button class="bg-blue-500 text-white rounded-full p-0.5">
                        <Icon class="w-8 h-8" icon="ic:round-plus" />
                    </button>
                    <div v-if="isOpen" class="mt-2 text-center">
                        <h5 class="text-xl font-bold text-gray-600">
                            Create new task
                        </h5>
                        <span class="text-xs text-gray-400 font-semibold"
                            >Or use invite link</span
                        >
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import { Icon } from "@iconify/vue";
import { ref } from "vue";
import SideBarLink from "./SideBarLink.vue";

const isOpen = ref(true);
</script>
