# anti-raid-test
em this is a test thingy so yea + this isnt mine lol code:

const { Client } = require("discord.js");
const client = new Client();


const { AntiRaid } = require("djs-antiraid"); // import djs-antiraid

const antiRaid = new AntiRaid(client, {
    rateLimit: 3, // Rate limit of actions.
    time: 30000, // Amount of time (in milliseconds)
    punishType: "removeRole", // ban, kick, editRole, removeRole
    verbose: true, // Extended Logs from module.
    ignoredUsers: [], // Array of User IDs that get ignored.
    ignoredRoles: [], // Array of Role IDs that get ignored.
    ignoredEvents: [] 
});



antiRaid.on("trying", (member, event, punishType) => {
    console.log(`I will trying do ${punishType} to stop ${member.user.tag} for ${event}`);
});

antiRaid.on("action", (member, type) => {
    console.log(`${member.user.tag} has been ${type}`);
});



client.on("ready", () => {
    console.log("Ready!");
});

client.login("YOUR_TOKEN_HERE");


