<script>
  import { Router, Route } from "svelte-routing";

  // components for this layout
  import AdminNavbar from "components/Navbars/AdminNavbar.svelte";
  import Sidebar from "components/Sidebar/Sidebar.svelte";
  import HeaderStats from "components/Headers/HeaderStats.svelte";
  import FooterAdmin from "components/Footers/FooterAdmin.svelte";

  // pages for this layout
  import Dashboard from "views/admin/Dashboard.svelte";
  import Settings from "views/admin/Settings.svelte";
  import Tables from "views/admin/Tables.svelte";
  import Containers from "views/admin/Containers.svelte";
  import Images from "views/admin/Images.svelte";

  export let location;
  export let admin = "";
</script>

<div>
  <Sidebar location={location}/>
  <div class="relative md:ml-64 bg-gray-200">
    <AdminNavbar />
    <HeaderStats />
    <div class="px-4 md:px-10 mx-auto w-full -m-24">
      <Router url="/">
        <Route path="dashboard" component="{Dashboard}" />
        <Route path="containers" component="{Containers}" />
        <Route path="images" component="{Images}" />
        <Route path="tables" component="{Tables}" />
        <Route path="settings" component="{Settings}" />
      </Router>
      <FooterAdmin />
    </div>
  </div>
</div>
