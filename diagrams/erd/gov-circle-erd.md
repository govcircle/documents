classDiagram
direction BT
class action {
   integer dropped_epoch
   integer enacted_epoch
   integer expired_epoch
   integer expiry_epoch
   integer ratified_epoch
   integer submission_epoch
   integer vote_abstain
   integer vote_no
   integer vote_yes
   timestamp(6) created_at
   bigint created_by_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) action_type
   varchar(255) cert_index
   varchar(255) deposit_amount
   varchar(255) ip
   varchar(255) stake_address
   varchar(255) status
   varchar(255) tag
   varchar(255) title
   varchar(255) tx_hash
   bigint id
}
class amendment {
   bigint constitution_id
   timestamp(6) created_at
   bigint created_by_id
   bigint opinion_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) amendment_type
   varchar(255) ip
   text src_rules
   text target_rules
   bigint id
}
class application_user {
   smallint status
   timestamp(6) created_at
   bigint created_by_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) email
   varchar(255) ip
   varchar(255) nonce
   varchar(255) user_address
   varchar(255) username
   bigint id
}
class application_user_authorities {
   bigint application_user_id
   varchar(255) authorities
}
class application_user_user_roles {
   bigint application_user_id
   bigint user_roles_id
}
class constitution {
   timestamp(6) created_at
   bigint created_by_id
   bigint gov_action_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) data_hash
   varchar(255) ip
   varchar(255) script
   varchar(255) url
   jsonb certificate
   bigint id
}
class merge_request {
   timestamp(6) created_at
   bigint created_by_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) ip
   bigint id
}
class opinion {
   timestamp(6) created_at
   bigint created_by_id
   bigint owner_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) intention
   varchar(255) ip
   varchar(255) status
   text user_act
   bigint id
}
class role {
   timestamp(6) created_at
   bigint created_by_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) ip
   varchar(255) title
   bigint id
}
class role_authorities {
   bigint role_id
   varchar(255) authorities
}
class rule {
   timestamp(6) created_at
   bigint created_by_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) ip
   varchar(255) rule
   varchar(255) status
   bigint id
}
class rule_change_history {
   bigint base_rule_id
   timestamp(6) created_at
   bigint created_by_id
   bigint revised_rule_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) amendment_type
   varchar(255) ip
   bigint id
}
class user_role {
   integer end_epoch
   integer start_epoch
   timestamp(6) created_at
   bigint created_by_id
   bigint role_id
   timestamp(6) updated_at
   bigint updated_by_id
   bigint user_id
   varchar(255) actor_registration_status
   varchar(255) ip
   bigint id
}
class voting_threshold {
   integer percentage
   timestamp(6) created_at
   bigint created_by_id
   bigint role_id
   timestamp(6) updated_at
   bigint updated_by_id
   varchar(255) action_type
   varchar(255) ip
   bigint id
}

action  -->  application_user : created_by_id:id
action  -->  application_user : updated_by_id:id
amendment  -->  application_user : created_by_id:id
amendment  -->  application_user : updated_by_id:id
amendment  -->  constitution : constitution_id:id
amendment  -->  opinion : opinion_id:id
application_user  -->  application_user : created_by_id:id
application_user  -->  application_user : updated_by_id:id
application_user_authorities  -->  application_user : application_user_id:id
application_user_user_roles  -->  application_user : application_user_id:id
application_user_user_roles  -->  user_role : user_roles_id:id
constitution  -->  action : gov_action_id:id
constitution  -->  application_user : updated_by_id:id
constitution  -->  application_user : created_by_id:id
merge_request  -->  application_user : created_by_id:id
merge_request  -->  application_user : updated_by_id:id
opinion  -->  application_user : created_by_id:id
opinion  -->  application_user : updated_by_id:id
opinion  -->  application_user : owner_id:id
role  -->  application_user : updated_by_id:id
role  -->  application_user : created_by_id:id
role_authorities  -->  role : role_id:id
rule  -->  application_user : updated_by_id:id
rule  -->  application_user : created_by_id:id
rule_change_history  -->  application_user : updated_by_id:id
rule_change_history  -->  application_user : created_by_id:id
user_role  -->  application_user : updated_by_id:id
user_role  -->  application_user : user_id:id
user_role  -->  application_user : created_by_id:id
user_role  -->  role : role_id:id
voting_threshold  -->  application_user : updated_by_id:id
voting_threshold  -->  application_user : created_by_id:id
voting_threshold  -->  role : role_id:id
