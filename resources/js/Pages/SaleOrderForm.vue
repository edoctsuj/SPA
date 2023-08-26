<template>
    <div>
        <!-- start header -->
        <div class="p-2 pt-2 bg-grey">
            <nav aria-label="breadcrumb">
                <ol class="fs-3 breadcrumb">
                    <li class="breadcrumb-item">Sales Orders</li>
                    <li class="breadcrumb-item active" aria-current="page">New</li>
                </ol>
            </nav>
            <div>
                <button type="button" class="btn btn-primary mr-10px">
                    Save
                </button>
                <button type="button" class="btn btn-secondary">Discard</button>
            </div>
        </div>
        <!-- end header -->

        <!-- start nav -->
        <div class="custom-border bg-white">
            <div class="mx-2 d-flex justify-content-lg-between align-items-center flex-wrap">
                <div class="d-flex align-items-center flex-wrap">
                    <button type="button" class="my-1 my-lg-0 btn btn-primary mr-10px">
                        Send by Email
                    </button>
                    <button type="button" class="my-1 my-lg-0 btn btn-primary mr-10px">
                        Print
                    </button>
                    <button type="button" class="my-1 my-lg-0 btn btn-secondary mr-10px">
                        Confirm Sale
                    </button>
                    <button type="button" class="my-1 my-lg-0 btn btn-secondary mr-10px">
                        Cancel
                    </button>
                </div>
                <div class="h-50px btn-group btn-breadcrumb breadcrumb-default">
                    <button type="button" class="btn btn-default grey">
                        Quotation
                    </button>
                    <button type="button" class="btn btn-default">
                        Quotation Sent
                    </button>
                    <button type="button" class="btn btn-default">
                        Sales Order
                    </button>
                </div>
            </div>
        </div>
        <!-- end nav -->

        <!-- start body -->
        <div class="bg-grey d-flex justify-content-center">
            <div class="bg-light container m-5">
                <h2>New</h2>
                <form>
                    <div class="row">
                        <div class="col-md-6">
                            <div class="form-group row mb-3">
                                <label for="staticEmail" class="col-sm-3 col-form-label">Customer</label>
                                <div class="col-sm-9">
                                    <select class="form-select" aria-label="Default select example">
                                        <option selected></option>
                                        <option value="1">One</option>
                                        <option value="2">Two</option>
                                        <option value="3">Three</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group row mb-3">
                                <label for="staticEmail" class="col-sm-3 col-form-label">Branch</label>
                                <div class="col-sm-9">
                                    <select class="form-select" aria-label="Default select example">
                                        <option selected></option>
                                        <option value="1">One</option>
                                        <option value="2">Two</option>
                                        <option value="3">Three</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="form-group row mb-3">
                                <label for="staticEmail" class="col-sm-3 col-form-label">Expiration Date</label>
                                <div class="col-sm-9">
                                    <select class="form-select" aria-label="Default select example">
                                        <option selected></option>
                                        <option value="1">One</option>
                                        <option value="2">Two</option>
                                        <option value="3">Three</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group row mb-3">
                                <label for="staticEmail" class="col-sm-3 col-form-label">Pricelist</label>
                                <div class="col-sm-9">
                                    <select class="form-select" aria-label="Default select example">
                                        <option selected></option>
                                        <option value="1">One</option>
                                        <option value="2">Two</option>
                                        <option value="3">Three</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group row mb-3">
                                <label for="staticEmail" class="col-sm-3 col-form-label">Payment Terms</label>
                                <div class="col-sm-9">
                                    <select class="form-select" aria-label="Default select example">
                                        <option selected></option>
                                        <option value="1">One</option>
                                        <option value="2">Two</option>
                                        <option value="3">Three</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                    </div>

                    <ul class="nav nav-tabs mt-3">
                        <li class="nav-item" v-for="(tab, index) in tabs" :key="index">
                            <a class="nav-link" :class="{ active: activeTab === index }" @click="changeTab(index)"
                                href="#">{{ tab }}</a>
                        </li>
                    </ul>

                    <div class="tab-content mt-3">
                        <div v-for="(tab, index) in tabs" :key="index"
                            :class="['tab-pane', { active: activeTab === index, show: activeTab === index }]">

                            <!-- start order lines -->
                            <template v-if="tab === 'Order Lines'">
                                <div class="row">
                                    <div class="col-md-6">
                                        <h3>Shipping Information</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Warehouse</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Shipping Policy</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <h3>Sales Information</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Salesperson</label>
                                            <div class="col-sm-9 d-flex align-items-center">
                                                <select class="form-select custom-form-select"
                                                    aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                                <span class="fs-4 bi bi-box-arrow-up-right"></span>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Sales Channel</label>
                                            <div class="col-sm-9 d-flex align-items-center">
                                                <select class="form-select custom-form-select"
                                                    aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                                <span class="fs-4 bi bi-box-arrow-up-right"></span>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Customer
                                                Reference</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row mt-5">
                                    <div class="col-md-6">
                                        <h3>Invoicing</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Order Date</label>
                                            <div class="col-sm-9">
                                                <VueDatePicker v-model="date"></VueDatePicker>

                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Fiscal Position</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </template>
                            <!-- end order lines -->

                            <!-- start other lines -->
                            <template v-else-if="tab === 'Other Lines'">
                                <p>This is the content for {{ tab }}</p>
                                <div class="row">
                                    <div class="col-md-6">
                                        <h3>Shipping Information</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Warehouse</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Shipping Policy</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-md-6">
                                        <h3>Sales Information</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Salesperson</label>
                                            <div class="col-sm-9 d-flex align-items-center">
                                                <select class="form-select custom-form-select"
                                                    aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                                <span class="fs-4 bi bi-box-arrow-up-right"></span>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Sales Channel</label>
                                            <div class="col-sm-9 d-flex align-items-center">
                                                <select class="form-select custom-form-select"
                                                    aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                                <span class="fs-4 bi bi-box-arrow-up-right"></span>
                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Customer
                                                Reference</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row mt-5">
                                    <div class="col-md-6">
                                        <h3>Invoicing</h3>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Order Date</label>
                                            <div class="col-sm-9">
                                                <VueDatePicker v-model="date"></VueDatePicker>

                                            </div>
                                        </div>
                                        <div class="form-group row mb-3">
                                            <label for="staticEmail" class="col-sm-3 col-form-label">Fiscal Position</label>
                                            <div class="col-sm-9">
                                                <select class="form-select" aria-label="Default select example">
                                                    <option selected></option>
                                                    <option value="1">One</option>
                                                    <option value="2">Two</option>
                                                    <option value="3">Three</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </template>
                            <!-- end other lines -->
                        </div>
                    </div>
                </form>
            </div>
        </div>
        <!-- end body -->

    </div>
</template>


<script>
import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'


export default {
    components: {
        VueDatePicker,
    },
    data() {
        return {
            tabs: ['Order Lines', 'Other Lines'],
            activeTab: 0,
            date: null,
        };
    },
    methods: {
        changeTab(index) {
            this.activeTab = index;
        },
    },
};
</script>
<style>
.bg-grey {
    background-color: #E6E6E6;
}

.custom-border {
    border-top: #adadad 1px solid;
    border-bottom: #adadad 1px solid;
}

.mr-10px {
    margin-right: 10px;
}

.h-50px {
    height: 50px;
}

.custom-form-select {
    width: 80% !important;
    margin-right: 10px !important;
}

.btn-group> :not(.btn-check:first-child)+.btn,
.btn-group>.btn-group:not(:first-child) {
    margin-left: 10px;
}

.btn-breadcrumb {
    background-color: #fff;
    border-radius: 0;
    border-left: solid 1px #ccc;
    outline-color: transparent;
    box-shadow: none;
}

.btn-breadcrumb * {
    border: none;
}

.btn-breadcrumb .btn:after,
.btn-breadcrumb .btn:before {
    content: " ";
    border-top: 25px solid transparent;
    border-bottom: 25px solid transparent;
    position: absolute;
    top: 50%;
    margin-top: -25px;
    left: 100%;
    z-index: 3;
}

.btn-breadcrumb .btn:after {
    border-left: 17px solid white;
    margin-left: -1px;
}

.btn-breadcrumb .btn:before {
    border-left: 17px solid rgb(173, 173, 173);
    margin-left: 0px;
}

.btn-breadcrumb .btn:last-child:after,
.btn-breadcrumb .btn:last-child:before {
    content: none;
}

.btn-breadcrumb .grey,
.btn-breadcrumb .grey:active {
    background-color: #e6e6e6;
    border-radius: 0;
    outline: none;
}

.btn-breadcrumb .grey:after {
    border-left: 10px solid #e6e6e6;
}

.btn-breadcrumb .grey:before {
    border-left: 10px solid #adadad;
}
</style>
