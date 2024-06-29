<script setup>
import Navbar from '@/components/Navbar.vue'
import {
    Dialog,
    DialogContent,
    DialogDescription,
    DialogFooter,
    DialogHeader,
    DialogTitle,
    DialogTrigger
} from '@/components/ui/dialog'
</script>

<template>
    <Navbar />
    <Dialog>
        <DialogTrigger as-child>
            <button variant="outline"> Edit Profile </button>
        </DialogTrigger>
        <DialogContent class="sm:max-w-[425px]">
            <DialogHeader>
                <DialogTitle>Edit profile</DialogTitle>
                <DialogDescription>
                    Make changes to your profile here. Click save when you're done.
                </DialogDescription>
            </DialogHeader>
            <div class="grid gap-4 py-4">
                <div class="grid grid-cols-4 items-center gap-4">
                    <label for="name" class="text-right"> Name </label>
                    <input id="name" value="Pedro Duarte" class="col-span-3" />
                </div>
                <div class="grid grid-cols-4 items-center gap-4">
                    <label for="username" class="text-right"> Username </label>
                    <input id="username" value="@peduarte" class="col-span-3" />
                </div>
            </div>
            <DialogFooter>
                <button type="submit"> Save changes </button>
            </DialogFooter>
        </DialogContent>
    </Dialog>
</template>
