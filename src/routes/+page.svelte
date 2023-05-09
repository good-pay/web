<script>
    import BusinessBanksToggle from "../components/BusinessBanksToggle.svelte";
    import BusinessHero from "../components/BusinessHero.svelte";
    import BankHero from "../components/BankHero.svelte";
    import {bankOrBusiness} from "../stores/bankOrBusiness";

    let forBankOrBusiness;
    bankOrBusiness.subscribe(value => {
        forBankOrBusiness = value;
    })
</script>
<div>
    <div class="navbar bg-base-100">
        <div class="flex-1">
            <h1><a href="/"
                   class="btn btn-ghost normal-case text-5xl text-bold {forBankOrBusiness ? 'text-info': 'text-success'}">Good
                Pay</a></h1>
        </div>
        <BusinessBanksToggle/>
    </div>
    {#if !forBankOrBusiness}
        <BusinessHero/>
    {:else }
        <BankHero/>
    {/if}
</div>
