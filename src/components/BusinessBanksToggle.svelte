<script>
    import {bankOrBusiness} from "../stores/bankOrBusiness";

    let forBanksOrBusinesses;

    bankOrBusiness.subscribe(value => {
        forBanksOrBusinesses = value;
    });

    const onToggle = () => {
        bankOrBusiness.update((value) => !value);
    };
</script>

<div class="flex-none gap-2">
    <h3 class="text-2xl font-bold {forBanksOrBusinesses ? '' : 'text-success'}">For Businesses</h3>
    <div class="form-control">
        <input bind:checked={forBanksOrBusinesses} on:change={onToggle}
               class="navbar-toggle toggle-info toggle toggle-lg"
               type="checkbox"
               id="business-bank-toggle"/>
    </div>
    <h3 class="text-2xl font-bold {forBanksOrBusinesses ? 'text-info' : ''}">For Banks</h3>
</div>
